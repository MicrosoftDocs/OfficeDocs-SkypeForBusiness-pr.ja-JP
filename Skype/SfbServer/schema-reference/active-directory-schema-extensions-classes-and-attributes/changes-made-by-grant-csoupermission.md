---
title: Skype の許可-CsOUPermission によるビジネス サーバーの変更
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Skype ビジネス サーバー管理を委任するにフォレストの準備によって作成された RTC ユニバーサル グループのメンバーは、Domain Admins グループのメンバーでなくて、Ou をアクセスできるように指定した組織単位 (Ou) へのアクセス許可を追加できます。
ms.openlocfilehash: 1313394248da2dcaeb9843bd689b2e2da3c51f96
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Skype の許可-CsOUPermission によるビジネス サーバーの変更
 
Skype ビジネス サーバー管理を委任するにフォレストの準備によって作成された RTC ユニバーサル グループのメンバーは、Domain Admins グループのメンバーでなくて、Ou をアクセスできるように指定した組織単位 (Ou) へのアクセス許可を追加できます。 
  
**許可 CsOuPermission**コマンドレットでは、次の表で指定されている指定した OU 内のオブジェクトへのアクセス許可を付与します。
  
## <a name="granting-permission-for-user-objects"></a>ユーザー オブジェクトに対するアクセス許可を付与します。

OU のユーザー オブジェクトの**Grant CsOuPermission**コマンドレットを実行すると、グループに次の表に示すようにアクセス許可が与えられます。
  
**ユーザー オブジェクトのアクセス許可**

|**グループ**|**アクセス許可**|**適用されます。**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更をレプリケートします。  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> パブリック情報の読み取り  <br/> 全般的な情報を読み取る  <br/> ユーザー ・ アカウントの制限の読み取り  <br/> |ユーザー オブジェクトの子孫  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet を記述します。  <br/> MsExchUCVoiceMailSettings を記述します。  <br/> RTCUserProvisioningPropertySet を記述します。  <br/> RTCPropertySet を記述します。  <br/> ProxyAddresses を記述します。  <br/> |ユーザー オブジェクトの子孫  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>コンピューター オブジェクトに対するアクセス許可を付与します。

OU にコンピューター オブジェクトの**Grant CsOuPermission**コマンドレットを実行すると、グループに次の表に示すようにアクセス許可が与えられます。
  
**コンピューター オブジェクトのアクセス許可**

|**グループ**|**アクセス許可**|**適用されます。**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更をレプリケートします。  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |パブリック情報の読み取り  <br/> 検証-DNS のホスト名を読み取る  <br/> |コンピューター オブジェクトの子孫  <br/> |
|RTCUniversalUserAdmins  <br/> |パブリック情報の読み取り  <br/> 検証-DNS のホスト名を読み取る  <br/> |コンピューター オブジェクトの子孫  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>連絡先または AppContact オブジェクトに対するアクセス許可を付与します。

次の表に示すように、OU の連絡先オブジェクトまたは AppContact オブジェクトの**Grant CsOuPermission**コマンドレットを実行するときに、グループでアクセス許可が付与します。
  
**取引先担当者または AppContact オブジェクトのアクセス許可**

|**グループ**|**アクセス許可**|**適用されます。**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更をレプリケートします。  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> パブリック情報の読み取り  <br/> 全般的な情報を読み取る  <br/> 個人情報を読み取る  <br/> ユーザー ・ アカウントの制限の読み取り  <br/> |連絡先オブジェクトの子孫  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet を記述します。  <br/> OtherIpPhone を記述します。  <br/> 表示名を書き込み  <br/> 説明を記述します。  <br/> 勤務先を記述します。  <br/> MsExchUCVoiceMailSettings を記述します。  <br/> RTCUserProvisioningPropertySet を記述します。  <br/> RTCPropertySet を記述します。  <br/> ProxyAddresses を記述します。  <br/> |連絡先オブジェクトの子孫  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>デバイス オブジェクトに対するアクセス許可を付与します。

OU のデバイス オブジェクトの**Grant CsOuPermission**コマンドレットを実行すると、グループに次の表に示すようにアクセス許可が与えられます。
  
**デバイス オブジェクトに与えられるアクセス許可**

|**グループ**|**アクセス許可**|**適用されます。**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更をレプリケートします。  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> パブリック情報の読み取り  <br/> 個人情報を読み取る  <br/> 全般的な情報を読み取る  <br/> ユーザー ・ アカウントの制限の読み取り  <br/> |連絡先オブジェクトの子孫  <br/> |
|RTCUniversalUserAdmins  <br/> |子を作成します。  <br/> 子を削除します。  <br/> ツリーを削除します。  <br/> |連絡先  <br/> |
|RTCUniversalUserAdmins  <br/> |表示名を書き込み  <br/> 説明を記述します。  <br/> 勤務先を記述します。  <br/> |ユーザー オブジェクトの子孫  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet を記述します。  <br/> OtherIpPhone を記述します。  <br/> 表示名を書き込み  <br/> 説明を記述します。  <br/> 勤務先を記述します。  <br/> MsExchUCVoiceMailSettings を記述します。  <br/> RTCUserProvisioningPropertySet を記述します。  <br/> RTCPropertySet を記述します。  <br/> ProxyAddresses を記述します。  <br/> |連絡先オブジェクトの子孫  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson オブジェクトに対するアクセス許可を付与します。

InetOrgPerson オブジェクトの**Grant CsOuPermission**コマンドレットを実行するには OU で、グループに次の表に示すように、アクセス許可が与えられます。
  
**InetOrgPerson オブジェクトに与えられるアクセス許可**

|**グループ**|**アクセス許可**|**適用されます。**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |ディレクトリ変更をレプリケートします。  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |内容の一覧表示  <br/> すべてのプロパティを読み取り  <br/> 読み取りアクセス許可  <br/> |このオブジェクトのみ  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet を読む  <br/> RTCUserProvisioningPropertySet を読む  <br/> RTCPropertySet を読む  <br/> 個人情報を読み取る  <br/> パブリック情報の読み取り  <br/> 全般的な情報を読み取る  <br/> ユーザー ・ アカウントの制限の読み取り  <br/> |子孫 inetOrgPerson オブジェクト  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet を記述します。  <br/> RTCUserProvisioningPropertySet を記述します。  <br/> RTCPropertySet を記述します。  <br/> ProxyAddresses を記述します。  <br/> |子孫 inetOrgPerson オブジェクト  <br/> |
   

