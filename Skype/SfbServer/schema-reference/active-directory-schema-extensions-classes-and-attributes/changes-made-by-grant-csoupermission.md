---
title: Skype for Business Server の権限付与によって行われた変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Skype for Business Server の管理を委任するために、フォレストの準備で作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずに Ou にアクセスできるように、指定された組織単位 (Ou) にアクセス許可を追加できます。
ms.openlocfilehash: 48c5921cabf2b1bc8100f796d3e3b7f6a247ff0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296694"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Skype for Business Server の権限付与によって行われた変更
 
Skype for Business Server の管理を委任するために、フォレストの準備で作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーにならずに Ou にアクセスできるように、指定された組織単位 (Ou) にアクセス許可を追加できます。 
  
**Grant-CsOuPermission**コマンドレットは、次の表に示すように、指定した OU 内のオブジェクトへのアクセス許可を付与します。
  
## <a name="granting-permission-for-user-objects"></a>ユーザーオブジェクトのアクセス許可の付与

OU 上のユーザーオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。
  
**ユーザーオブジェクトに付与される権限**

|**化**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリの変更の複製  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> 公開-情報を読む  <br/> 一般的な情報を読む-情報  <br/> ユーザーアカウントの制限を読む  <br/> |子孫のユーザーオブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> MsExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> ProxyAddresses の書き込み  <br/> |子孫のユーザーオブジェクト  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>コンピューターオブジェクトへのアクセス許可の付与

OU 上のコンピューターオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。
  
**コンピューターオブジェクトに付与される権限**

|**化**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリの変更の複製  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |公開-情報を読む  <br/> 読み取り済みの DNS ホスト名  <br/> |子コンピューターオブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |公開-情報を読む  <br/> 読み取り済みの DNS ホスト名  <br/> |子コンピューターオブジェクト  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Contact オブジェクトまたは AppContact オブジェクトのアクセス許可を付与する

組織内の連絡先オブジェクトまたは AppContact オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。
  
**Contact オブジェクトまたは AppContact オブジェクトに付与されているアクセス許可**

|**化**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリの変更の複製  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> 公開-情報を読む  <br/> 一般的な情報を読む-情報  <br/> 個人情報を読む  <br/> ユーザーアカウントの制限を読む  <br/> |子孫の連絡先オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> 他の Ip電話を書く  <br/> DisplayName を書く  <br/> 説明の書き込み  <br/> TelephoneNumber の書き込み  <br/> MsExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> ProxyAddresses の書き込み  <br/> |子孫の連絡先オブジェクト  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>デバイスオブジェクトのアクセス許可の付与

OU 上のデバイスオブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。
  
**デバイスオブジェクトに付与されるアクセス許可**

|**化**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリの変更の複製  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> 公開-情報を読む  <br/> 個人情報を読む  <br/> 一般的な情報を読む-情報  <br/> ユーザーアカウントの制限を読む  <br/> |子孫の連絡先オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |子の作成  <br/> 子の削除  <br/> ツリーの削除  <br/> |問い合わせ  <br/> |
|RTCUniversalUserAdmins  <br/> |DisplayName を書く  <br/> 説明の書き込み  <br/> TelephoneNumber の書き込み  <br/> |子孫のユーザーオブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> 他の Ip電話を書く  <br/> DisplayName を書く  <br/> 説明の書き込み  <br/> TelephoneNumber の書き込み  <br/> MsExchUCVoiceMailSettings の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> ProxyAddresses の書き込み  <br/> |子孫の連絡先オブジェクト  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトのアクセス許可を付与する

OU 上の InetOrgPerson オブジェクトに対して**Grant-CsOuPermission**コマンドレットを実行すると、次の表に示すように、グループにアクセス許可が付与されます。
  
**InetOrgPerson オブジェクトに対して付与されるアクセス許可**

|**化**|**アクセス許可**|**適用対象**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリの変更の複製  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |リストの内容  <br/> すべてのプロパティを読み上げる  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> 個人情報を読む  <br/> 公開-情報を読む  <br/> 一般的な情報を読む-情報  <br/> ユーザーアカウントの制限を読む  <br/> |子の inetOrgPerson オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet の書き込み  <br/> RTCUserProvisioningPropertySet の書き込み  <br/> RTCPropertySet の書き込み  <br/> ProxyAddresses の書き込み  <br/> |子の inetOrgPerson オブジェクト  <br/> |
   

