

# 编译modem
在modem目录下执行：
1. ./make.sh "MLT6753_65C_L1(LWG_DSDS).mak" new   编译modem文件
2. ../alps/device/mediatek/build/build/tools/modemRenameCopy.pl . MLT6753_65C_L1\(LWG_DSDS\) ：将编译生成的文件重命名
3. 替换modem文件（路径：*alps/vendor/mediatek/proprietary/custom/mlt6735m_65u_l1/modem/mlt6735m_65u_l_lwg_dsds/*）
4. 去掉旧的AP文件

## 6.0编译 modem技巧 ##
如果是打PATCH，需要删除modem下之前的MDDB和DB文件
有脚本的项目可以使用脚本编译modem，该脚本可以自动编译modem并copy到vendor/mediatek/proprietary/custom/mlt6755_65u_m/modem/mt6755_sp_lwctg_mp2_umoly0020下
```
./copyresult_malata.sh -cm
```
>该脚本部分内容为
```
function compile_copy_modem()
{
cd ../modem/mcu/
MAKE_NAME=$(ls make/projects/ | grep mak)
echo --------------start compiling modem--------------
echo ./m \"$MAKE_NAME\" new ...!
./m $MAKE_NAME new
echo --------------compile modem finished!--------------
echo --------------start coping modem--------------
cd ../../alps/
./device/mediatek/build/build/tools/modemRenameCopy.pl ../modem/mcu $MAKE_NAME

cd vendor/mediatek/proprietary/custom/$PROJECT_TARGET/modem/$MODEM_NAME/
find . ! -iname md1arm7.img | xargs rm -f
cd -
cp ../modem/mcu/temp_modem/* vendor/mediatek/proprietary/custom/$PROJECT_TARGET/modem/$MODEM_NAME/
ls -l vendor/mediatek/proprietary/custom/$PROJECT_TARGET/modem/$MODEM_NAME/
echo --------------copy modem finished--------------
}
```
------------------------------

# 编译差分包
1. make otapackage
2. 制作差分包
```
 ./build/tools/releasetools/ota_from_target_files  -i  v1.zip v2.zip update.zip  （使用默认签名）
 ./build/tools/releasetools/ota_from_target_files –k <key_path> -i  V1_org.zip V2_org.zip V1_2.zip  （使用客户签名）
```
* 如果 MTK_SIGNATURE_CUSTOMIZATION=yes 并且MTK_INTERNAL=no：
          <key_path>的值为：build/target/product/security/[Project]/releasekey
* 如果MTK_SIGNATURE_CUSTOMIZATION=yes并且MTK_INTERNAL=yes：
          <key_path>的值为：build/target/product/security/common/releasekey
* 如果MTK_SIGNATURE_CUSTOMIZATION=no，<key_path>的值为：build/target/product/security/testkey
v1.zip 路径 ： *out/target/product/$(project)/obj/PACKAGING/target_files_intermediates/<project>_target_files-<user>.zip*

注：**M版本**加了几个参数，否则会无法生存scater文件导致升级失败：
```
./build/tools/releasetools/ota_from_target_files -s ./device/mediatek/build/releasetools/mt_ota_from_target_files --block -k <key_path> -i <老的ota升级包> <新的ota升级包> update.zip
```
###FOTA需继续执行以下三步
1. md5sum update.zip > md5sum   (修改md5sum多余字符串)
2. 修改md5sum多余字符串
3. zip  v1_2.zip update.zip md5sum

------------------------------
# 编译 kernel
make -j8 kernel 2>&1 | tee build.log

打包kernel成为可下载文件
make -j8 bootimage 2>&1 | tee build.log

------------------------------
# 黑科技
###空包测试
如果编译空包测试ota，则可以直接修改out目录下的配置文件中版本号，然后重新make otapackage
android L 修改位置 : *alps\out\target\product\project\system\build.prop*
android M 修改位置 : *alps\out\target\product\project\obj\ETC\system_build_prop_intermediates\build.prop*

------------------------------
# 升级Win10后FlashTools无法刷机
解决方法：高级启动，禁用驱动签名之后再安装驱动就阔以了

------------------------------
# SystemUI.apk快速验证方法
一般systemui需要push到手机中然后重启，重启时间很慢
改进：
```
adb push systemui.apk system/priv-app/SystemUI
adb shell
ps | grep systemui
kill -9 {pid}
```
------------------------------
#User-Debug版本调试
```
adb disable-verity
adb reboot  
adb remount
//每次开机都需要执行root
```
------------------------------
#Android N编译报错ninja: fatal: fork: Cannot allocate memory
解决办法：
```
$export JACK_SERVER_VM_ARGUMENTS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4g"
$./prebuilts/sdk/tools/jack-admin kill-server
$./prebuilts/sdk/tools/jack-admin start-server  
```
------------------------------
