---
title: Skype for Business Server Grant-CsOUPermissionによって行われた変更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Skype for Business Server の管理を委任するには、フォレストの準備によって作成された RTC ユニバーサル グループのメンバーが Domain Admins グループのメンバーでなくても、その US にアクセスできるよう、指定した組織単位 (US) にアクセス許可を追加できます。
ms.openlocfilehash: 09a6d6baf554b18db0a388619ffb74c85c6963fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831847"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Skype for Business Server Grant-CsOUPermissionによって行われた変更
 
Skype for Business Server の管理を委任するには、フォレストの準備によって作成された RTC ユニバーサル グループのメンバーが Domain Admins グループのメンバーでなくても、その US にアクセスできるよう、指定した組織単位 (US) にアクセス許可を追加できます。 
  
**Grant-CsOuPermission** コマンドレットは、次の表で指定されているように、指定された OU 内のオブジェクトへのアクセス許可を付与します。
  
## <a name="granting-permission-for-user-objects"></a>ユーザー オブジェクトに対するアクセス許可の付与

OU 上のユーザー オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。
  
**ユーザー オブジェクトに対して付与されるアクセス許可**

|**グループ**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更のレプリケート  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet の読み取り  <br/> RTCUserProvisioningPropertySet の読み取り  <br/> RTCPropertySet の読み取り  <br/> Public-Information の読み取り  <br/> General-Information の読み取り  <br/> User-Account-Restrictions の読み取り  <br/> |子ユーザー オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> msExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> proxyAddresses の書き込み  <br/> |子ユーザー オブジェクト  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>コンピューター オブジェクトに対するアクセス許可の付与

OU 上のコンピューター オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。
  
**コンピューター オブジェクトに対して付与されるアクセス許可**

|**グループ**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更のレプリケート  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Public-Information の読み取り  <br/> Validated-DNS-Host-Name の読み取り  <br/> |子のコンピューター オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |Public-Information の読み取り  <br/> Validated-DNS-Host-Name の読み取り  <br/> |子のコンピューター オブジェクト  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>連絡先または AppContact オブジェクトに対するアクセス許可の付与

OU 上の連絡先オブジェクトまたは AppContact オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。
  
**連絡先または AppContact オブジェクトに対して付与されるアクセス許可**

|**グループ**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更のレプリケート  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet の読み取り  <br/> RTCUserProvisioningPropertySet の読み取り  <br/> RTCPropertySet の読み取り  <br/> Public-Information の読み取り  <br/> General-Information の読み取り  <br/> Personal-Information の読み取り  <br/> User-Account-Restrictions の読み取り  <br/> |子連絡先オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> otherIpPhone の書き込み  <br/> displayName の書き込み  <br/> description の書き込み  <br/> telephoneNumber の書き込み  <br/> msExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> proxyAddresses の書き込み  <br/> |子連絡先オブジェクト  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>デバイス オブジェクトに対するアクセス許可の付与

OU 上のデバイス オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。
  
**デバイス オブジェクトに対して付与されるアクセス許可**

|**グループ**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更のレプリケート  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet の読み取り  <br/> RTCUserProvisioningPropertySet の読み取り  <br/> RTCPropertySet の読み取り  <br/> Public-Information の読み取り  <br/> Personal-Information の読み取り  <br/> General-Information の読み取り  <br/> User-Account-Restrictions の読み取り  <br/> |子連絡先オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |子の作成  <br/> 子の削除  <br/> ツリーの削除  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |displayName の書き込み  <br/> description の書き込み  <br/> telephoneNumber の書き込み  <br/> |子ユーザー オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> otherIpPhone の書き込み  <br/> displayName の書き込み  <br/> description の書き込み  <br/> telephoneNumber の書き込み  <br/> msExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> proxyAddresses の書き込み  <br/> |子連絡先オブジェクト  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトに対するアクセス許可の付与

OU 上の InetOrgPerson オブジェクトに対して **Grant-CsOuPermission** コマンドレットを実行すると、次の表で示すように、グループにアクセス許可が付与されます。
  
**InetOrgPerson オブジェクトに対して付与されるアクセス許可**

|**グループ**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更のレプリケート  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティの読み取り  <br/> アクセス許可の読み取り  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet の読み取り  <br/> RTCUserProvisioningPropertySet の読み取り  <br/> RTCPropertySet の読み取り  <br/> Personal-Information の読み取り  <br/> Public-Information の読み取り  <br/> General-Information の読み取り  <br/> User-Account-Restrictions の読み取り  <br/> |子 inetOrgPerson オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> proxyAddresses の書き込み  <br/> |子 inetOrgPerson オブジェクト  <br/> |
   

