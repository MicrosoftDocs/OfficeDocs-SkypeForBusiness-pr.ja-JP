---
title: グローバル スコープとタグ スコープを使用するコマンドレット
TOCTitle: グローバル スコープとタグ スコープを使用するコマンドレット
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56270054
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グローバル スコープとタグ スコープを使用するコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

Skype for Business Online では、ポリシーはグローバル スコープとタグ スコープ (またはユーザーごとのスコープ) のいずれかで構成できます。**Get-Cs** コマンドレットを使用する場合はスコープまたは ID を指定する必要はありません。パラメーターを指定せずにこれらのコマンドレットのいずれかを呼び出すと、関連するすべての項目が返されます。たとえば、次のコマンドは、すべての外部アクセス ポリシーに関する情報を返します。

    Get-CsExternalAccessPolicy

返されるデータを制限する場合、含める必要があるのは Identity パラメーターまたは Filter パラメーターのみです。たとえば、グローバル ポリシーのみを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "global"

ID "RedmondAccessPolicy" が含まれるユーザーごとのポリシーを返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"

> [!NOTE]
> ユーザーごとのポリシーを参照する場合、タグ <strong>プレフィクス</strong>は省略可能です。プレフィクスが含まれる次の構文も有効です。<br />
> Get-CsExternalAccessPolicy –Identity &quot;tag:RedmondAccessPolicy&quot;


グローバル ポリシーを除くすべてのポリシー (つまり、すべてのユーザーごとのポリシー) を返すには、次のコマンドを使用します。

    Get-CsExternalAccessPolicy -Filter "tag:*"

次のコマンドレットは、グローバル スコープとユーザーごと (タグ) スコープの両方に対して機能します。

  - [Get-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClientPolicy)

  - [Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy)

  - [Get-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDialPlan)

  - [Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

  - [Get-CsPresencePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPresencePolicy)

  - [Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)

> [!NOTE]
> ダイヤル プランは、名前とは異なり、機能的にはポリシーです。たとえば、ダイヤル プランという用語はダイヤル ポリシーの代わりに使用されていますが、これは以前のバージョンの Lync Server で使用された用語を保持するためです。


## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

