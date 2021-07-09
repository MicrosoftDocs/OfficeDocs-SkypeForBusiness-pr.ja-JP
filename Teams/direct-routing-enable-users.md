---
title: ユーザーに直接ルーティングを有効にする
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: システム ダイレクト ルーティングを使用してユーザー Microsoft 電話する方法について説明します。
ms.openlocfilehash: 86132778226702577068d9502ae46cba949667c6
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345713"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする

この記事では、直接ルーティングでユーザーを有効にする電話システム説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。

- 手順 1. [Connect システムを使用して SBC Microsoft 電話し、接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順 2.ダイレクト ルーティング、音声、ボイスメールのユーザーを有効にする**   (この記事)
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md) 


ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。

ユーザーが直接ルーティングを有効にする準備ができたら、次の手順に従います。 

1. ユーザーを管理者またはMicrosoft 365作成Office 365ライセンスを割り電話システムします。 
2. ユーザーがオンラインでホームSkype for Businessします。 
3. 電話番号を構成し、エンタープライズ音声とボイスメールを有効にする。 
4. ユーザーにTeamsのみモードを割り当てる。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成してライセンスを割り当てる

新しいユーザーを作成するには、2 つのオプションMicrosoft 365またはOffice 365。 ただし、ルーティングの問題を回避するために、組織で 1 つのオプションを選択する必要があります。 

- オンプレミスの Active Directory にユーザーを作成し、そのユーザーをクラウドと同期します。 「[オンプレミスのディレクトリを Azure Active Directory」を参照してください](/azure/active-directory/connect/active-directory-aadconnect)。
- ユーザーを作成するには、Microsoft 365 管理センター。 「[ユーザーを個別に、または一括でユーザーを追加する」Microsoft 365または Office 365 - 管理者向けヘルプ を参照してください](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

Skype for Business Online の展開がオンプレミスの Skype for Business 2015 または Lync 2010 または 2013 と共存している場合、サポートされている唯一のオプションは、オンプレミスの Active Directory にユーザーを作成し、ユーザーをクラウドと同期することだけです (オプション 1)。 

ライセンス要件の詳細については、「直接ルーティングの計画」の「ライセンスと[他の](direct-routing-plan.md#licensing-and-other-requirements)[要件」を参照してください](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online"></a>ユーザーがオンラインでホームに設定されている 

この手順は、有効なユーザー Skype for Business Server エンタープライズ VoIP直接ルーティングに移行Teams適用されます。

ダイレクト ルーティングでは、ユーザーをオンラインでホームに設定する必要があります。 RegistrarPool パラメーターを確認すると確認できます。このパラメーターには、infra.lync.com があります。 また、ユーザーを直接ルーティングに移行するときに、LineURI の管理をオンプレミスからオンラインに変更Teamsです。 

1. Connect Online PowerShell Skype for Businessセッションを作成します。

2. コマンドを発行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet が False に設定され、LineUri に <E.164 電話番号> が設定されている場合、電話番号はオンプレミスに割り当て済みであり、O365 に同期されます。 電話番号をオンラインで管理する場合は、Skype for Business Online PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business Management Shell を使用してパラメーターをクリーンアップし、O365 と同期します。 

1. 管理Skype for Businessコマンドを発行します。 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > EnterpriseVoiceEnabled を False に設定する必要はありません。レガシ Skype for Business 電話が使用され、テナント ハイブリッド構成が UseOnPremDialPlan $True で設定されている場合、ダイヤル プランの正規化の問題が発生する可能性があります。 
    
   変更が同期された後、 のOffice 365の出力は `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 次の結果です。

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > オンプレミスの電話属性を削除する前に、すべてのユーザーの電話属性をオンライン[で管理Skype for Businessがあります](/skypeforbusiness/hybrid/decommission-on-prem-overview)。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a>電話番号を構成し、エンタープライズ音声とボイスメールをオンラインで有効にする 

ユーザーを作成し、ライセンスを割り当てた後、次の手順では、ユーザーのオンライン電話設定を構成します。 

 
1. Connect Online PowerShell Skype for Businessセッションを作成します。 

2. ユーザーの電話番号をオンプレミスで管理する場合は、次のコマンドを発行します。 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. ユーザーの電話番号をオンラインで管理する場合は、次のコマンドを発行します。 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次を入力します。 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張子を持つ同じ基本番号を共有している場合は、次を入力します。
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    使用する電話番号が国コードを含む完全な E.164 電話番号として構成されていることをお勧めしますが、必須ではありません。 ベース番号に対する検索で複数の結果が返された場合にユーザーを参照するために使用される内線番号を使用して電話番号を構成できます。 これにより、会社は同じ基本番号と一意の内線番号を持つ電話番号を構成できます。 ルックアップを成功するには、次のように、招待に拡張子を含む完全な番号を含める必要があります。
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business Management Shell またはコントロール パネルを使用して、ユーザーの電話番号を構成します。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>ボイスメールへの通話の直接送信の構成

ダイレクト ルーティングを使用すると、ユーザーへの呼び出しを終了し、ユーザーのボイスメールに直接送信できます。 通話をボイスメールに直接送信する場合は、opaque=app:voicemail を Request URI ヘッダーにアタッチします。 たとえば、"sip:user@yourdomain.com;opaque=app:voicemail" などです。 この場合、ユーザー Teams通知を受信しない場合、通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>ユーザーにTeamsモードを割り当て、通話が確実に着信Microsoft Teams

直接ルーティングでは、ユーザーが着信Teamsクライアントに着信通話が確実に着信Teams必要があります。 ユーザーを [のみ] Teamsするには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。 詳細については、「IT 管理者向け [アップグレード戦略」を参照してください](upgrade-to-teams-on-prem-implement.md)。 組織で Skype for Business Server または Skype for Business Online を使用している場合、Skype と Teams の間の相互運用性については、Skype for Business の移行と相互運用性に関する記事[を参照してください](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
