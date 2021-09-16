# 科技服务队维基百科·WindowsSystem    

本章主要记录windows系统相关问题，包括但不限于
* windows系统激活相关 
* windows系统崩溃相关



## 利用KMS服务器激活Windows 
### 说明 
此方法适用于校园网或其他假设有KMS服务器的环境下的系统激活，同时也可以用于家庭版系统升级专业版。需注意使用KMS服务激活的系统每半年需要连接一次KMS服务器，否则会提示系统未激活。 

需注意，查阅资料发现部分OEM预装Windows不支持使用KMS激活。当然，对于有OEM正版系统的计算机不建议使用KMS服务器激活。 
### 详细步骤   
对于KMS激活的系统，其密钥是统一的，只会随着系统版本的不同而有所变化：
```
Win10专业版KMS： W269N-WFGWX-YVC9B-4J6C9-T83GX 
Win10企业版KMS： NPPR9-FWDCX-D2C8J-H872K-2YT43 
Win10LTSB版KMS： DCPHK-NFMTC-H88MJ-PFHPY-QJ4BJ 
Win10家庭版KMS： TX9XD-98N7V-6WMQ6-BX7FG-H8Q99 
Win10教育版KMS： NW6C2-QMPVW-D7KKK-3GKT6-VCFB2 
Win7专业版KMS： FJ82H-XT6CR-J8D7P-XQJJ2-GPDD4 
Win7企业版KMS： 33PXH-7Y6KF-2VJC9-XBBR8-HVTHH 
```

因此，使用CMD或powershell配置slmgr：

```
slmgr /upk #uninstall current KEY
slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX #install Pro version KMS key
slmgr /skms "KMSserverip:1688" #set KMS IP & port
slmgr /ato 
```