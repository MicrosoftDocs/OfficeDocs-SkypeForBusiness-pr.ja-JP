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
description: Microsoft Phone System Direct Routing を有効にする方法について説明します。
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421312"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>ユーザーに直接ルーティング、音声、ボイスメールを有効にする

この記事では、ユーザーが電話システムダイレクト ルーティングを有効にする方法について説明します。  これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。

- 手順 1. [SBC を Microsoft Phone System に接続し、接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順 2.ユーザーに直接ルーティング、音声、ボイスメールを有効にする**   (この記事)
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に翻訳する](direct-routing-translate-numbers.md) 


ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングを構成する」を [参照してください](direct-routing-configure.md)。

ユーザーに直接ルーティングを有効にする準備ができたら、次の手順を実行します。 

1. Microsoft 365 または Office 365 でユーザーを作成し、電話システム ライセンスを割り当てる。 
2. ユーザーが Skype for Business Online にホームとして登録されている必要があります。 
3. 電話番号を構成し、エンタープライズボイスメールとボイスメールを有効にする。 
4. Teams Only モードをユーザーに割り当てる。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成してライセンスを割り当てる 

Microsoft 365 または Office 365 で新しいユーザーを作成するには、2 つのOfficeがあります。 ただし、ルーティングの問題を回避するには、組織で 1 つのオプションを選択する必要があります。 

- オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。 「 [オンプレミスのディレクトリを Azure Active Directory と統合する」を参照してください](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- Microsoft 365 管理センターでユーザーを直接作成します。 「Microsoft [365 または Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)にユーザーを個別または一括で追加する - 管理者向けヘルプ」を参照してください。 

Skype for Business Online 展開が Skype for Business 2015 または Lync 2010 または 2013 オンプレミスと共存している場合、サポートされる唯一のオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期することだけです (オプション 1)。 

ライセンス要件の詳細については、「プラン ダイレクト ルーティング」のライセンスと他[の](direct-routing-plan.md#licensing-and-other-requirements)[要件を参照してください](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>ユーザーがオンラインで自宅にいて、電話番号がオンプレミスから同期されていない (Skype for Business Server エンタープライズ VoIP でユーザーを Teams ダイレクト ルーティングに移行できる)

直接ルーティングを使用するには、ユーザーをオンラインで使用する必要があります。 RegistrarPool パラメーター (ドメイン内に値が必要) を調infra.lync.comできます。 OnPremLineUriManuallySet パラメーターも True に設定する必要があります。 これは、電話番号を構成し、Skype for Business Online PowerShell を使用してエンタープライズボイスメールとボイスメールを有効にすることで実現されます。

1. Skype for Business Online PowerShell セッションに接続します。

2. コマンドを発行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet が False に設定され、LineUri に <E.164 電話番号> が設定されている場合は、Skype for Business Online PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business 管理シェルを使用してパラメーターをクリーンアップしてください。 

1. Skype for Business 管理シェルからコマンドを発行します。 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   変更が 365 に同期Office、期待される出力は `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 次の結果です。

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>電話番号を構成し、エンタープライズボイスメールとボイスメールを有効にする 

ユーザーを作成し、ライセンスを割り当てしたら、次の手順では、ユーザーの電話番号とボイスメールを構成します。 

電話番号を追加してボイスメールを有効にするには:
 
1. Skype for Business Online PowerShell セッションに接続します。 

2. コマンドを発行します。 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次を入力します。 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張子を持つ同じベース番号を共有する場合は、次を入力します。
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    使用する電話番号が国コードを含む完全な E.164 電話番号として構成されていることをお勧めしますが、必須ではありません。 ベース番号に対する参照が複数の結果を返す場合にユーザーを参照するために使用される内線番号を使用して電話番号を構成することができます。 これにより、会社は同じ基本番号と一意の内線番号を持つ電話番号を構成できます。 参照を成功するには、招待には、次のように、拡張子が付く完全な番号を含める必要があります。
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロール パネルを使用して、ユーザーの電話番号を構成します。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>ボイスメールに通話を直接送信する構成

直接ルーティングを使用すると、ユーザーへの通話を終了し、ユーザーのボイスメールに直接送信することができます。 通話をボイスメールに直接送信する場合は、OPAQUE=app:voicemail を Request URI ヘッダーに添付します。 たとえば、"sip:user@yourdomain.com;opaque=app:voicemail" などです。 この場合、Teams ユーザーは通話通知を受け取り、通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Teams Only モードをユーザーに割り当て、通話が確実に Microsoft Teams に着信する

直接ルーティングでは、ユーザーが Teams クライアントに着信通話を確実に発信するには、Teams Only モードである必要があります。 ユーザーを Teams のみモードにする場合は、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。 詳細については [、IT 管理者向けアップグレード戦略を参照してください](upgrade-to-teams-on-prem-implement.md)。 組織で Skype for Business Server または Skype for Business Online を使用している場合、Skype と Teams の相互運用性については、次の記事を参照してください [。Skype for Business](migration-interop-guidance-for-teams-with-skype.md)との移行と相互運用性。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
