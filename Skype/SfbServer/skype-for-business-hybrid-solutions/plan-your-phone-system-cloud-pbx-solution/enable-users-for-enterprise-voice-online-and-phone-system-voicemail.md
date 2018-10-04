---
title: エンタープライズ VoIP でオンラインと Office 365 のボイスメールに電話システムのユーザーを有効にします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: ビジネス ユーザー向けに、Skype のインターネット電話サービスを Office 365 に電話システムを有効にする方法を説明します。
ms.openlocfilehash: ec0e37c0597f81001075f144dd38b58acfbb1159
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372671"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>エンタープライズ VoIP でオンラインと Office 365 のボイスメールに電話システムのユーザーを有効にします。
 
ビジネス ユーザー向けに、Skype のインターネット電話サービスを Office 365 に電話システムを有効にする方法を説明します。
  
設置した PSTN 接続を Office 365 に電話システムを展開する最後の手順は、Office 365 とボイスメールの電話システムのユーザーを有効にするのには。 これらの機能を有効にするには、Office 365 の全体管理者の役割を持つユーザーであり、リモート PowerShell を実行できる必要があります。 Skype for Business Online でエンタープライズ VoIP がまだ有効でないユーザー アカウントに対して、このトピックの手順を実行する必要があります。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Office 365 のインターネット電話サービスの電話システムを有効にします。

Office 365 のボイスとボイス メールの電話システムで、ユーザーを有効にするのには、Skype のビジネス オンラインのコネクタは、サーバーに展開するを参照して、ホスト ボイス メールに対してユーザーを有効にするチェックのように、いくつかの初期手順を実行する必要があります。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Office 365 のボイスとボイス メールの電話システムのユーザーを有効にするには

1. 作業を開始する前に、ビジネス オンライン コネクタ (Windows PowerShell モジュール) の Skype がフロント エンド サーバーで運用されていることを確認します。 そうでない場合は、[ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=39366)からダウンロードできます。 このモジュールを使用して、 [Skype のオンライン ビジネスの管理には、コンピューター](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)を構成する方法の詳細が表示されます。
    
2. 管理者として、Windows Powershell を起動します。
    
3. 次のコマンドを入力し、Enter キーを押します。
    
   ```
   Import-Module skypeonlineconnector
   ```

4. 次のコマンドを入力し、Enter キーを押します。
    
   ```
   $cred = Get-Credential
   ```

    Enter キーを押すと、[Windows PowerShell 資格情報の要求] ダイアログ ボックスが表示されます。
    
5. テナント管理者のユーザー名とパスワードを入力し、[**OK**] をクリックします。
    
6. PowerShell ウィンドウで、次のコマンドを入力し、Enter キーを押します。
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 次のコマンドレットを入力して、セッションをインポートします。
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    実行すると、PowerShell、Skype のビジネス サーバーのビジネス コマンドレットをローカルの Skype は既に読み込まれて PowerShell を開いたとき。 同じ名前のオンプレミスのコマンドレットを上書きするオンラインのコマンドレットを使用するのには、AllowClobber パラメーターを指定する必要があります。
    
8. Set-CsUser コマンドレットを使用して、次のように、$EnterpriseVoiceEnabled および $HostedVoiceMail プロパティをユーザーに割り当てます。
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例:
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > SIP アドレス、ユーザー プリンシパル名 (UPN)、ドメイン名とユーザー名 (domain\username)、および Active Directory での表示名 ("小林 良太") でユーザーを指定することもできます。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>回線 URI を更新し、ダイヤル プランを有効にして Office 365 の電話システムのユーザーの

このセクションでは、行の URI を更新し、ダイヤル プランを有効にして Office 365 の電話システムのユーザーの方法を説明します。 
  
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

ユーザーごとに Windows PowerShell と[与える CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットのダイヤル プランを割り当てることができます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー 2015 または Windows PowerShell のリモート セッションから。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>単一のユーザーにユーザー単位のダイヤル プランを割り当てるには

- [許可 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用して、Ken Myer のユーザーにユーザーごとのダイヤル プラン RedmondDialPlan を割り当てます。
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>複数のユーザーにユーザー単位のダイヤル プランを割り当てるには

- 次のコマンドは、ユーザーごとのダイヤル プラン RedmondDialPlan を、Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される、LdapFilter パラメーターの詳細については、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメントを参照してください。
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> グローバルまたはユーザーのダイヤル プランを、オンライン ユーザーに対して使用することができます。サイトのダイヤル プランはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>ユーザー単位のダイヤル プランの割り当てを解除するには

- Ken Myer に割り当てられていたすべてのユーザーごとのダイヤル プランの割り当てを解除する[許可 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps)コマンドレットを使用します。 ユーザーごとのダイヤル プランの割り当てが解除されると、Ken Myer は自動的にグローバル ダイヤル プランまたはこのユーザーの拡張レジストラーまたは PSTN ゲートウェイに割り当てられたサービス スコープのダイヤル プランを使用して管理されるようになります。 サービス スコープのダイヤル プランはグローバル ダイヤル プランより優先されます。
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>オンプレミスの Windows Powershell コマンドレットを使用して音声ルーティング ポリシーを更新するには

このセクションでは、Office 365 の電話システムが有効なユーザーの音声ルーティング ポリシーを更新する方法について説明します。
  
Office 365 ユーザーの電話システムには、呼び出しが正常にルーティングするために割り当てられている音声ルーティング ポリシーが必要です。 これは、呼び出しを適切にルーティングできるように割り当てる音声ポリシーを必要するオンプレミスの企業音声ユーザーとは異なります。 音声ルーティング ポリシーには、電話システムのユーザーの Office 365 で承認された呼び出しおよびルートを定義する PSTN 使用法が含まれている必要があります。 これらの PSTN 使用法は、既存の音声ポリシーから新しい音声ルーティング ポリシーにコピーできます。 詳細については、[新規 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)を参照してください。
  
> [!NOTE]
> Office 365 のユーザーにすべての電話システムが許可されている呼び出し元の機能を定義する BusinessVoice という名前の同じのオンラインの音声ポリシーに割り当てられてなどの同時呼び出しを許可します。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>単一のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには

- [許可 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、Ken Myer のユーザーに、ユーザーごとの音声ルーティング ポリシー RedmondVoiceRoutingPolicy を割り当てます。
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>複数のユーザーにユーザーごとの音声ルーティング ポリシーを割り当てるには

- 次のコマンドは、ユーザー単位の音声ルーティング ポリシー RedmondVoiceRoutingPolicy を Redmond 市で働くすべてのユーザーに割り当てます。 このコマンドで使用される、LdapFilter パラメーターの詳細については、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)を参照してください。
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > グローバルまたはユーザーの音声ルーティング ポリシーを、オンライン ユーザーに対して使用することができます。サイトの音声ルーティング ポリシーはこれらのユーザーに、オンプレミスでホストされオンプレミス サイトに割り当てられているユーザーに対して適用する目的だけで使用することはできません。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>ユーザー単位の音声ルーティング ポリシーを割り当て解除するには

- 許可-CsVoiceRoutingPolicy を使用して、Ken Myer に割り当てられていたすべてのユーザーごとの音声ルーティング ポリシーの割り当てを解除します。 ユーザー単位の音声ルーティング ポリシーが割り当て解除された後、Ken Myer は、グローバル音声ルーティング ポリシーによって、自動的に管理されます。
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    詳細については、[補助金 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)を参照してください。
    

