---
title: エンタープライズ VoIP オンラインおよび電話システムのボイスメールのユーザーを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Skype for Business ユーザーに対して電話システム音声サービスを有効にする方法について学習します。
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098573"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>エンタープライズ VoIP オンラインおよび電話システムのボイスメールのユーザーを有効にする
 
> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

Skype for Business ユーザーに対して電話システム音声サービスを有効にする方法について学習します。
  
オンプレミスの PSTN 接続を使用して電話システムを展開する最後の手順は、ユーザーが電話システムとボイスメールを有効にするための手順です。 これらの機能を有効にするには、グローバル管理者の役割を持つユーザーであり、リモート PowerShell を実行できる必要があります。 Skype for Business Online で有効になっていないすべてのユーザー アカウントについて、このトピックエンタープライズ VoIPする必要があります。
  
## <a name="enable-phone-system-voice-services"></a>電話システム音声サービスを有効にする

ユーザーが電話システムボイスメールとボイスメールを有効にするには、Skype for Business Online Connector がサーバーに展開され、ユーザーがホストされたボイスメールを有効にするための確認など、いくつかの初期手順を実行する必要があります。
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>ユーザーが電話システムの音声とボイスメールを有効にするには

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールの一部です。
> 最新の [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック リリースを使用している場合は、Skype for Business Online Connector をインストールする必要があります。

1. 開始する前に、Teams PowerShell モジュールがフロントエンド サーバーにインストールされていることを確認します。 インストールされていない場合は、「Teams PowerShell モジュールのインストール」の手順 [に従ってインストールしてください](/microsoftteams/teams-powershell-install)。
    
2. 管理者Windows PowerShell開始します。
    
3. 次を入力し、Enter キーを押します。
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. 次のように、Set-CsUserコマンドレットを使用して、$EnterpriseVoiceEnabledプロパティ$HostedVoiceMailをユーザーに割り当てる。
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > また、ユーザーを SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory の表示名 ("Bob Kelly") で指定することもできます。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>電話システムで有効になっているユーザーの回線 URI とダイヤル プランを更新する

このセクションでは、電話システムで有効になっているユーザーの回線 URI とダイヤル プランを更新する方法について説明します。 
  
### <a name="to-update-the-line-uri"></a>Line URI を更新するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート] メニューまたはデスクトップ ショートカットを使用して、Skype for Business Server コントロール パネルを開きます。
    
    > [!NOTE]
    > ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開く方法もできます。 
  
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表で、回線 URI を変更する Skype for Business ユーザー アカウントをクリックします。
    
6. [ **回線 URI]** をクリックし、正規化された一意の電話番号 (tel:+14255550200 など) を入力します。 次に、[ **コミット] をクリックします**。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスのコマンドレットを使用してダイヤル プランWindows PowerShellする

ユーザー単位のダイヤル プランは、Windows PowerShell [Grant-CsDialPlan コマンドレットを使用して割り当](/powershell/module/skype/grant-csdialplan?view=skype-ps) てできます。 このコマンドレットは、Skype for Business Server 2015 から実行するか、Skype for Business Server 2015 のリモート セッションから実行Windows PowerShell。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>ユーザー単位のダイヤル プランを 1 人のユーザーに割り当てるには

- [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤル プラン RedmondDialPlan をユーザー Ken Myer に割り当てる。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザーごとのダイヤル プランを割り当てるには

- 次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てします。 このコマンドで使用される LdapFilter パラメーターの詳細については [、Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) コマンドレットのドキュメントを参照してください。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> オンライン ユーザーには、グローバル ダイヤル プランまたはユーザー ダイヤル プランを使用できます。 サイト ダイヤル プランは、オンプレミスでホストされ、オンプレミス サイトに割り当てられているユーザーにのみ適用されます。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>ユーザーごとのダイヤル プランの割り当てを解除するには

- [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、Ken Myer に以前割り当てられたユーザーごとのダイヤル プランの割り当てを解除します。 ユーザーごとのダイヤル プランが割り当て解除された後、Ken Myer は、自分のレジストラーまたは PSTN ゲートウェイに割り当てられたグローバル ダイヤル プランまたはサービス スコープダイヤル プランを使用して自動的に管理されます。 サービス スコープダイヤル プランは、グローバル ダイヤル プランよりも優先されます。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスのコマンドレットを使用して音声ルーティング ポリシー Windows PowerShellする

このセクションでは、電話システムで有効になっているユーザーの音声ルーティング ポリシーを更新する方法について説明します。
  
電話システム のユーザーは、通話が正常にルーティングするために、音声ルーティング ポリシーが割り当てられている必要があります。 これは、通話を正常にルーティングするために音声ポリシーを割り当てる必要があるオンプレミスのビジネス音声ユーザーとは異なります。 音声ルーティング ポリシーには、電話システム ユーザーの承認された通話とルートを定義する PSTN 使用法が含まれている必要があります。 これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティング ポリシーにコピーできます。 詳細については [、「New-CsVoiceRoutingPolicy」を参照してください](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> すべての電話システム ユーザーには、許可されている通話機能を定義する BusinessVoice という名前の同じオンライン音声ポリシーが割り当てられます。たとえば、同時呼び出しを許可します。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>ユーザー単位の音声ルーティング ポリシーを 1 人のユーザーに割り当てるには

- [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーごとの音声ルーティング ポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てる。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>ユーザー単位の音声ルーティング ポリシーを複数のユーザーに割り当てるには

- 次のコマンドは、ユーザーごとの音声ルーティング ポリシー RedmondVoiceRoutingPolicy を、Redmond 市で働くすべてのユーザーに割り当てる。 このコマンドで使用される LdapFilter パラメーターの詳細については [、「Get-CsUser」を参照してください](/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > オンライン ユーザーには、グローバルまたはユーザーの音声ルーティング ポリシーを使用できます。 サイト音声ルーティング ポリシーは、オンプレミスでホストされ、オンプレミス サイトに割り当てられているユーザーにのみ適用されます。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>ユーザーごとの音声ルーティング ポリシーの割り当てを解除するには

- Ken Myer に以前Grant-CsVoiceRoutingPolicy割り当てられたユーザーごとの音声ルーティング ポリシーの割り当てを解除するには、このオプションを使用します。 ユーザーごとの音声ルーティング ポリシーが割り当て解除された後、Ken Myer はグローバル音声ルーティング ポリシーを使用して自動的に管理されます。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    詳細については [、「Grant-CsVoiceRoutingPolicy」を参照してください](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
