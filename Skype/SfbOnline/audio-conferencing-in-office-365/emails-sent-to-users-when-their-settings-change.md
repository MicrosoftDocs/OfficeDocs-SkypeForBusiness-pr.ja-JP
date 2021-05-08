---
title: Skype for Business Online で設定が変更された場合にユーザーに送信されるメール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Online でダイヤルイン会議の設定が変更された場合に、ユーザーにメールで自動的に送信される情報についてSkype for Businessします。 '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237343"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Skype for Business Online で設定が変更された場合にユーザーに送信されるメール

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams で自動メール情報を探している場合は、「Microsoft Teams で設定が変更された場合にユーザーに送信されるメール」[を参照Microsoft Teams。](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)

電子メールは、電話会議プロバイダーとして Microsoft[](set-up-audio-conferencing.md)を使用して電話会議が有効になっているユーザーに自動的に送信されます。
  
既定では、電話会議が有効になっているユーザーに送信される 4 種類のメールがあります。 ただし、ユーザーに送信されるメールの数を制限する場合は、オフにできます。 次の場合、Microsoft 365またはOffice 365電話会議は、ユーザーのメールにメールを送信します。
  
- **電話会議ライセンスが割り当てられるか、電話会議プロバイダーを Microsoft に変更するときに割り当てられます。**
    
     このメールには、会議 ID、会議の既定の電話会議電話番号、ユーザーの電話会議 PIN、ユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれます。 「[ライセンスを割りSkype for Business割り当てる」](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)または[「Microsoft を電話会議プロバイダーとして割り当てる」を参照してください](assign-microsoft-as-the-audio-conferencing-provider.md)。
    
    > [!NOTE]
    > 組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。 組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。 
  
    このメールの例を次に示します。
    
     ![Skype for Businessライセンスの確認](../images/audio-conferencing-user-enabled.png)
  
    追加ライセンスの詳細については、「Skype for Businessライセンス」をSkype for Business[参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
- **ユーザーの会議 ID または既定の電話会議電話番号が変更されます。**
    
    このメールには、会議 ID、既定の電話会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれている。 ただし、このメールにはユーザーの電話会議 PIN は含めになっていません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。
    
    > [!NOTE]
    > 組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。 組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。 
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議情報が変更されました。](../images/audio-conferencing-info-change.png)
  
- **ユーザーの電話会議 PIN がリセットされます。**
    
    このメールには、開催者の電話会議 PIN、既存の会議 ID、ユーザーの既定の電話会議電話番号が含まれている。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。
    
    > [!NOTE]
    > 組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。 組織で [電話会議の動的な ID を設定できます](./reset-a-conference-id-for-a-user.md)。 
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議 PIN が変更されました。](../images/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスが削除される、または電話会議プロバイダーが Microsoft から他のプロバイダーまたはなしに変更された場合。**
    
    これは、電話会議ライセンスがユーザーから削除された場合、またはユーザーの電話会議プロバイダーを Microsoft からサードパーティの電話会議プロバイダーに変更する場合、またはプロバイダーを [なし] に設定するときに発生 **します**。 このメールには、ユーザーが Skype for Business Online Meeting Update Tool を使用して、既定の電話会議の電話番号や会議 ID などの電話会議固有の情報を削除する手順と情報が記載されています。
    
    「ライセンス[の割り当てまたは削除」をMicrosoft 365 Apps for business。](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)
    
    このメールの例を次に示します。
    
     ![ダイヤルイン会議は無効になります。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されるメール メッセージに変更を加える

[From] 連絡先情報に含まれるメール アドレスや表示名など、ユーザーに自動的に送信されるメール *を変更できます* 。 既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10))コマンドレットを使用して、メール アドレスと表示名を変更できます。 ユーザーにメールを送信するメール アドレスを変更するには、次の条件を実行する必要があります。
  
- _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
- _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
- _SendEmailOverride パラメーターを_ True に _設定します_。
    
次のコマンドを実行して、メールの送信先のメール アドレスやメールの表示名など、ユーザーに送信されたメールを変更できます。
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  メール アドレス情報を変更する場合は、環境の受信メール ポリシーで、アドレスから指定されたカスタムからのメールを許可する必要があります。 [From] 連絡先情報を上書 *き* する場合は、メールがユーザーに正しく送信されていることを確認する必要があります。 これを行うには、組織内の 1 人のユーザーでこれをテストします。
  
会議 ID をリセットする[](/previous-versions//mt228132(v=technet.10))
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合は、どうしますか?

ユーザーへのメール送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、電子メールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要な点として、電話会議 PIN はユーザーに送信されません。 この場合は、ユーザーに別のメールを送信するか、ユーザーに電話で通知する必要があります。
  
既定では、メールはユーザーに送信されますが、電話会議のメールを受信したくない場合は、Skype for Business 管理センターまたは Windows PowerShell を使用できます。 
 
![管理センターを使用Skype for Business ](../images/sfb-logo-30x30.png) **ロゴをSkype for Businessアイコン**  
    
1. **Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. **[Microsoft Bridge の設定] ページ** で、[電話会議の設定が変更された場合にユーザーにメールを自動的に送信する]**をオンまたはオフにします**。 
    
3. **[保存]** をクリックします。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Windows PowerShell を使用する**
  
1. 次のコマンドを実行して、すべてのユーザーのメール送信を無効にします。
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

会議 ID をリセットする[](/previous-versions//mt228132(v=technet.10))
  
## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- ユーザーへのメールの自動送信を有効または無効にする方法の詳細については、「電話会議の設定が変更された場合にメールの送信を有効または無効にする」 [を参照してください](enable-or-disable-sending-emails-when-their-settings-change.md)。
    
- ユーザーがオーディオ情報を失い、すべてのオーディオ情報をユーザーに送信できる必要がある場合があります。 これを行うには、Skype for Business 管理センターを使用し、ユーザーの電話会議プロパティの下にある [電子メールで電話会議情報を送信する] をクリックします。 「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。 ただし、この情報には電話会議 PIN は含まれます。
    
    送信されるこの電子メールの例を次に示します。
    
     ![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10))コマンドレットを使用して、メール アドレスと表示名を変更できます。
    
- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)
