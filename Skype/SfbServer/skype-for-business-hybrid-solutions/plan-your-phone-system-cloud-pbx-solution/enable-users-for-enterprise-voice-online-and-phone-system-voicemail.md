---
title: Office 365 ボイスメールのエンタープライズ Voip オンラインおよび電話システムでユーザーを有効にする
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
description: Skype for Business ユーザー用に Office 365 音声サービスの電話システムを有効にする方法について説明します。
ms.openlocfilehash: 8ed04e3926adfecb2f0022d12c783f6c3e83d763
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780726"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Office 365 ボイスメールのエンタープライズ Voip オンラインおよび電話システムでユーザーを有効にする
 
Skype for Business ユーザー用に Office 365 音声サービスの電話システムを有効にする方法について説明します。
  
オンプレミスの PSTN 接続を使用して Office 365 で電話システムを展開する最後の手順は、Office 365 およびボイスメールの電話システムでユーザーを有効にすることです。 これらの機能を有効にするには、グローバル管理者の役割を持つユーザーである必要があり、リモート PowerShell を実行できる必要があります。 Skype for Business Online でエンタープライズ Voip が有効になっていないすべてのユーザーアカウントについて、このトピックの手順を実行する必要があります。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Office 365 voice services で電話システムを有効にする

Office 365 音声およびボイスメールの電話システムに対してユーザーを有効にするには、最初の手順を実行する必要があります。これは、Skype for Business Online Connector がサーバーに展開されているかどうかを確認し、ユーザーがホストボイスメールを使用できるようにすることです。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Office 365 の電話システムでユーザーを有効にする音声とボイスメール

1. 開始する前に、Skype for Business Online Connector (Windows PowerShell モジュール) がフロントエンドサーバーに展開されていることを確認してください。 そうでない場合は、[ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=39366)からダウンロードできます。 このモジュールの使用の詳細については[、「Skype For Business Online 管理用のコンピューターの構成](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx)」を参照してください。
    
2. 管理者として Windows PowerShell を開始します。
    
3. 次のように入力し、enter キーを押します。
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 次のように入力し、enter キーを押します。
    
   ```powershell
   $cred = Get-Credential
   ```

    Enter キーを押すと、[Windows PowerShell 資格情報] ダイアログボックスが表示されます。
    
5. テナント管理者のユーザー名とパスワードを入力し、[ **OK]** をクリックします。
    
6. PowerShell ウィンドウで、次のように入力して enter キーを押します。
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 次のコマンドレットを入力して、セッションをインポートします。
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Skype for Business Server で PowerShell を実行している場合は、PowerShell を開いたときにローカルの Skype for Business コマンドレットが既に読み込まれています。 -AllowClobber パラメーターを指定して、オンラインコマンドレットが同じ名前でオンプレミスのコマンドレットを上書きできるようにする必要があります。
    
8. 次のように、$EnterpriseVoiceEnabled コマンドレットを使用して、ユーザーに $HostedVoiceMail プロパティを割り当てます。
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    以下に例を示します。
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > ユーザーの SIP アドレス、ユーザープリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory の表示名 ("Bob 友野") を使用して、ユーザーを指定することもできます。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Office 365 で電話システムが有効なユーザーの回線 URI とダイヤルプランを更新する

このセクションでは、Office 365 で電話システムが有効になっているユーザーの回線 URI とダイヤルプランを更新する方法について説明します。 
  
### <a name="to-update-the-line-uri"></a>行 URI を更新するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート] メニューまたはデスクトップショートカットを使用して、Skype for Business Server コントロールパネルを開きます。
    
    > [!NOTE]
    > ブラウザーウィンドウを開き、管理者の URL を入力して Skype for Business Server コントロールパネルを開くこともできます。 
  
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表で、回線 URI を変更する Skype for Business ユーザーアカウントをクリックします。
    
6. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel: + 14255550200) を入力します。 [**確定**] をクリックします。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスの Windows PowerShell コマンドレットを使用してダイヤルプランを更新する

Windows PowerShell と[get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。 このコマンドレットは、Skype for Business Server 2015 または Windows PowerShell のリモートセッションから実行できます。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>ユーザー単位のダイヤルプランを1人のユーザーに割り当てるには

- ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てるには、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用します。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザー単位のダイヤルプランを割り当てるには

- 次のコマンドは、Redmond の市区町村で働くすべてのユーザーに、ユーザーごとのダイヤルプラン RedmondDialPlan を割り当てます。 このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメント」を参照してください。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> オンラインユーザーには、グローバルまたはユーザーダイヤルプランのいずれかを使用できます。 サイトダイヤルプランは、社内でホストされ、オンプレミスサイトに割り当てられているユーザーにのみ適用されます。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>ユーザーごとのダイヤルプランの割り当てを解除するには

- 以前に Ken Myer に割り当てられたユーザーごとのダイヤルプランの割り当てを解除するには、 [get-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用します。 ユーザーごとのダイヤルプランの割り当てが解除されると、Ken Myer は、そのレジストラーまたは PSTN ゲートウェイに割り当てられたグローバルダイヤルプランまたはサービススコープのダイヤルプランを使用して、自動的に管理されます。 サービススコープのダイヤルプランは、グローバルダイヤルプランより優先されます。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスの Windows PowerShell コマンドレットを使用して音声ルーティングポリシーを更新する

このセクションでは、Office 365 で電話システムが有効になっているユーザーの音声ルーティングポリシーを更新する方法について説明します。
  
Office 365 の電話システムユーザーが正常にルーティングを行うには、ユーザーに音声ルーティングポリシーが割り当てられている必要があります。 これは、通話を正常にルーティングできるようにするために、音声ポリシーが割り当てられているオンプレミスのビジネスボイスユーザーとは異なります。 音声ルーティングポリシーには、Office 365 ユーザーの電話システムの承認済み呼び出しとルートを定義する PSTN 使用法を含める必要があります。 これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティングポリシーにコピーできます。 詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」を参照してください。
  
> [!NOTE]
> Office 365 のすべての電話システムユーザーには、許可される通話機能を定義する BusinessVoice という名前の同じオンライン音声ポリシーが割り当てられています。たとえば、同時呼び出しを許可します。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>ユーザー単位の音声ルーティングポリシーを単一のユーザーに割り当てるには

- ユーザーごとの音声ルーティングポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てるには、 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用します。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>ユーザー単位の音声ルーティングポリシーを複数のユーザーに割り当てるには

- 次のコマンドは、ユーザーごとの音声ルーティングポリシー RedmondVoiceRoutingPolicy を Redmond の市区町村で働くすべてのユーザーに割り当てます。 このコマンドで使用する LdapFilter パラメーターの詳細については、「 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」を参照してください。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > オンラインユーザーには、グローバルまたはユーザーの音声ルーティングポリシーを使用できます。 サイトの音声ルーティングポリシーは、社内でホストされ、オンプレミスサイトに割り当てられているユーザーにのみ適用されるため、使用できません。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>ユーザー単位の音声ルーティングポリシーの割り当てを解除するには

- Grant-csvoiceroutingpolicy を使用して、以前に Ken Myer に割り当てられたユーザーごとの音声ルーティングポリシーを割り当てを解除します。 ユーザー単位の音声ルーティングポリシーが割り当て解除されると、Ken Myer はグローバル音声ルーティングポリシーを使用して自動的に管理されます。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    詳細については、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)」を参照してください。
    

