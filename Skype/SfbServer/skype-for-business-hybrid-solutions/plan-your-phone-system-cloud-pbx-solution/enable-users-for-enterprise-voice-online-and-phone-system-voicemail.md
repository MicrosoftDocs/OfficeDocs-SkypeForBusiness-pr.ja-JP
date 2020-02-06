---
title: エンタープライズ VoIP オンラインおよび Office 365 ボイスメールの電話システムでユーザーを有効にする
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
description: Skype for Business ユーザー用に Office 365 voice services で電話システムを有効にする方法について説明します。
ms.openlocfilehash: f4fdd2a9a3da58f6804fa65acf96ba2b8fac682e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802207"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>エンタープライズ VoIP オンラインおよび Office 365 ボイスメールの電話システムでユーザーを有効にする
 
Skype for Business ユーザー用に Office 365 voice services で電話システムを有効にする方法について説明します。
  
Office 365 でオンプレミスの PSTN 接続を使用して電話システムを展開するための最後の手順は、Office 365 およびボイスメールの電話システムでユーザーを有効にすることです。 これらの機能を有効にするには、Office 365 の全体管理者の役割を持つユーザーであり、リモート PowerShell を実行できる必要があります。 Skype for Business Online でエンタープライズ VoIP がまだ有効でないユーザー アカウントに対して、このトピックの手順を実行する必要があります。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Office 365 voice services で電話システムを有効にする

Office 365 ボイスとボイスメールで電話システムのユーザーを有効にするには、最初の手順を実行する必要があります。これは、Skype for Business Online Connector がサーバーに展開されているかどうかの確認や、ユーザーがホスト型ボイスメールを有効にしているかどうかを確認する場合などです。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Office 365 ボイスメールとボイスメールでユーザーの電話システムを有効にするには

1. 作業を始める前に、Skype for Business Online Connector (Windows PowerShell モジュール) がフロントエンドサーバーに展開されていることを確認します。 そうでない場合は、[ダウンロードセンター](https://www.microsoft.com/en-us/download/details.aspx?id=39366)からダウンロードできます。 このモジュールの使用方法の詳細については、「 [Skype For Business Online の管理用にコンピューターを構成](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)する」を参照してください。
    
2. 管理者として、Windows Powershell を起動します。
    
3. 次のコマンドを入力し、Enter キーを押します。
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 次のコマンドを入力し、Enter キーを押します。
    
   ```powershell
   $cred = Get-Credential
   ```

    Enter キーを押すと、[Windows PowerShell 資格情報の要求] ダイアログ ボックスが表示されます。
    
5. テナント管理者のユーザー名とパスワードを入力し、[**OK**] をクリックします。
    
6. PowerShell ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 次のコマンドレットを入力して、セッションをインポートします。
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Skype for Business Server で PowerShell を実行している場合は、PowerShell を開いたときにローカルの Skype for Business コマンドレットが既に読み込まれています。 -AllowClobber パラメーターを指定して、オンラインのコマンドレットでオンプレミスのコマンドレットを同じ名前で上書きできるようにする必要があります。
    
8. Set-CsUser コマンドレットを使用して、次のように、$EnterpriseVoiceEnabled および $HostedVoiceMail プロパティをユーザーに割り当てます。
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory での表示名 ("小林 良太") でユーザーを指定することもできます。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Office 365 で有効になっている電話システムのユーザーのライン URI とダイヤルプランを更新する

このセクションでは、Office 365 の電話システムで有効になっているユーザーのために、行の URI とダイヤルプランを更新する方法について説明します。 
  
### <a name="to-update-the-line-uri"></a>回線 URI を更新するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. スタート メニューかデスクトップ ショートカットを使用して、Skype for Business Server のコントロール パネルを開きます。
    
    > [!NOTE]
    > また、ブラウザー ウィンドウを開いて管理 URL を入力し、Skype for Business Server のコントロール パネルを開くこともできます。 
  
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. 表で、回線 URI を変更する Skype for Business ユーザー アカウントをクリックします。
    
6. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力して、[**確定**] をクリックします。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスの Windows Powershell コマンドレットを使用してダイヤル プランを更新する

Windows PowerShell と[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。 このコマンドレットは、Skype for Business Server 2015 または Windows PowerShell のリモートセッションから実行できます。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>単一のユーザーにユーザー単位のダイヤル プランを割り当てるには

- [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てます。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザー単位のダイヤル プランを割り当てるには

- 次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」コマンドレットのドキュメントを参照してください。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> グローバルまたはユーザーのダイヤル プランを、オンライン ユーザーに対して使用することができます。サイトのダイヤル プランはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>ユーザー単位のダイヤル プランの割り当てを解除するには

- [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、以前に Ken Myer に割り当てられていたユーザーごとのダイヤルプランの割り当てを解除します。 ユーザーごとのダイヤル プランの割り当てが解除されると、Ken Myer は自動的にグローバル ダイヤル プランまたはこのユーザーの拡張レジストラーまたは PSTN ゲートウェイに割り当てられたサービス スコープのダイヤル プランを使用して管理されるようになります。 サービス スコープのダイヤル プランはグローバル ダイヤル プランより優先されます。
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスの Windows Powershell コマンドレットを使用して音声ルーティング ポリシーを更新するには

このセクションでは、Office 365 の電話システムを有効にしているユーザーのボイスルーティングポリシーを更新する方法について説明します。
  
Office 365 の電話システムユーザーが正常にルーティングするためには、それらにボイスルーティングポリシーが割り当てられている必要があります。 これは、呼び出しを適切にルーティングできるように割り当てる音声ポリシーを必要するオンプレミスの企業音声ユーザーとは異なります。 ボイスルーティングポリシーには、Office 365 ユーザーの電話システムに対して承認された通話とルートを定義する PSTN の使用状況が含まれている必要があります。 これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティング ポリシーにコピーできます。 詳細については、「[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」を参照してください。
  
> [!NOTE]
> Office 365 ユーザーのすべての電話システムには、利用可能な通話機能を定義するビジネス用ボイスと同じオンラインボイスポリシーが割り当てられています。たとえば、[同時呼び出しを許可する] を選びます。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>単一のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには

- [CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーごとのボイスルーティングポリシー RedmondVoiceRoutingPolicy をユーザー Ken Myer に割り当てます。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>複数のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには

- 次のコマンドは、ユーザー単位の音声ルーティング ポリシー RedmondVoiceRoutingPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)」を参照してください。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > グローバルまたはユーザーの音声ルーティング ポリシーを、オンライン ユーザーに対して使用することができます。サイトの音声ルーティング ポリシーはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>ユーザー単位の音声ルーティング ポリシーを割り当て解除するには

- CsVoiceRoutingPolicy を使用して、以前に Ken Myer に割り当てられているユーザーごとの音声ルーティングポリシーを割り当て解除します。 ユーザー単位の音声ルーティング ポリシーが割り当て解除された後、Ken Myer は、グローバル音声ルーティング ポリシーによって、自動的に管理されます。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    詳細については、「[Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)」を参照してください。
    

