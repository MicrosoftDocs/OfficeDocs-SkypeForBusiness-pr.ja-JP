---
title: ユーザー ID とタグ スコープを使用するコマンドレット
TOCTitle: ユーザー ID とタグ スコープを使用するコマンドレット
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56270062
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ユーザー ID とタグ スコープを使用するコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

(ユーザーにポリシーを割り当てるために使用される) **Grant-Cs** コマンドレットには、ユーザー ID (Identity パラメーター) と、ユーザーごとのポリシーの ID (PolicyName パラメーター) の 2 つの識別子が必要です。たとえば、音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てるには、次のコマンドを使用します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

ユーザーにポリシーを割り当てる際には、2 つの点を考慮する必要があります。まず、割り当てることができるのはユーザーごとのポリシーのみです。ユーザーにグローバル ポリシーを割り当てることはできません。たとえば、次のコマンドは失敗します。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

このコマンドが失敗するのは、グローバル ポリシーを割り当てる必要がないためです。グローバル ポリシーを使用してユーザーを管理する場合は、そのユーザーにユーザーごとのポリシーを割り当てないようにします。ユーザーに割り当てられているユーザーごとのポリシーがない場合、そのユーザーは自動的にグローバル ポリシーを使用して管理されます。

> [!NOTE]
> 以前、ユーザーにユーザーごとのポリシーが割り当てられていて、そのポリシーの割り当てを解除し、代わりにグローバル ポリシーによりユーザーを管理する場合を考えます。この場合、まず次の構文を使用します。この構文は、ユーザーに null ポリシーを付与して、ユーザーごとのポリシーの割り当てを解除します。<br />
> Grant-CsVoicePolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null


第 2 に、ユーザーごとのポリシーはタグ スコープで作成されることに留意します。ただし、ポリシー名を指定する場合にはタグ **プレフィクス**を省略できます。次の 2 つのコマンドは同じです。

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

すべてのユーザーごとのポリシー (または少なくとも、音声ポリシーなど、指定された種類のすべてのユーザーごとのポリシー) の ID を返すには、次のようなコマンドを使用します。

    Get-CsVoicePolicy -Filter "tag:*"

次のコマンドレットはユーザー ID とタグ スコープの両方を使用します。

  - [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)

  - [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy)

  - [Grant-CsDialPlan](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsDialPlan)

  - [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

  - [Grant-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsHostedVoicemailPolicy)

  - [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy)

## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

