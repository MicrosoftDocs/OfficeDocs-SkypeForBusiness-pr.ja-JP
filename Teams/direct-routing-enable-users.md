---
title: ユーザーが直接ルーティングできるようにする
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
description: Microsoft Phone システムのダイレクトルーティングを有効にする方法について説明します。
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655484"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする

この記事では、ユーザーが電話システムのダイレクトルーティングを有効にする方法について説明します。  これは、次の手順の手順2で、直接ルーティングを構成します。

- 手順1 [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順2ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする**   (この記事)
- 手順3 [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 


直接ルーティングを設定するために必要なすべての手順については、「 [直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

ユーザーに対して直接ルーティングを有効にする準備ができたら、次の手順を実行します。 

1. Microsoft 365 または Office 365 でユーザーを作成し、電話システムのライセンスを割り当てます。 
2. ユーザーが Skype for Business Online に所属していることを確認します。 
3. 電話番号を構成し、エンタープライズボイスとボイスメールを有効にします。 
4. チーム専用モードをユーザーに割り当てます。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成してライセンスを割り当てる 

Microsoft 365 または Office 365 で新規ユーザーを作成するには、2つのオプションがあります。 ただし、Microsoft は、ルーティングの問題を回避するためのオプションを組織で選ぶことをお勧めします。 

- オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。 「 [オンプレミスディレクトリと Azure Active Directory の統合」を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)参照してください。
- Microsoft 365 管理センターで直接ユーザーを作成します。 「 [Microsoft 365 または Office 365 にユーザーを個別に、または一括して追加する」を](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)参照してください。 

Skype for business Online の展開 coexists が Skype for Business 2015 または Lync 2010 または2013オンプレミスの場合、サポートされているオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドに同期することだけです (オプション 1)。 

ライセンス要件の詳細については、「[プランダイレクトルーティング](direct-routing-plan.md)の[ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」を参照してください。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>ユーザーがオンラインになっていて、電話番号がオンプレミスから同期されていないことを確認します (Skype for Business Server Enterprise Voice を有効にしたユーザーには、チームダイレクトルーティングに移行されます)。

直接ルーティングでは、ユーザーがオンラインである必要があります。 RegistrarPool パラメーターを確認すると、infra.lync.com ドメインで値を指定する必要があります。 Onpremlineurimanuます。また、Set パラメーターも True に設定する必要があります。 これは、Skype for Business Online PowerShell を使用して電話番号を設定し、エンタープライズボイスとボイスメールを有効にすることで実現されます。

1. Skype for Business Online PowerShell セッションに接続します。

2. 次のコマンドを実行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet が False に設定され、LineUri に <E.i 電話> 番号が設定されている場合は、Skype for Business Online PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business の管理シェルを使ってパラメーターを削除してください。 

1. Skype for Business の管理シェルから次のコマンドを実行します。 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   変更が Office 365 に同期された後、の予想される出力は次のようになり `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` ます。

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>電話番号を設定し、エンタープライズボイスとボイスメールを有効にする 

ユーザーを作成してライセンスを割り当てたら、次の手順では、ユーザーの電話番号とボイスメールを構成します。 

電話番号を追加してボイスメールを有効にするには:
 
1. Skype for Business Online PowerShell セッションに接続します。 

2. 次のコマンドを実行します。 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    たとえば、"Spencer Low" というユーザーの電話番号を追加するには、次のように入力します。 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    ユーザー "Spencer Low" と "Stacy Quinn" が、固有の拡張子を持つ同じ基本番号を共有している場合は、次のように入力します。
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    使用が推奨される電話番号は、国コードを含む完全な E.i 電話番号として構成することをお勧めしますが、必須ではありません。 基本番号に対する検索で複数の結果が返された場合に、ユーザーを検索するために使用される内線番号を使って電話番号を構成することができます。 これにより、会社は同じ基本番号と固有の内線番号で電話番号を構成できます。 検索を成功させるには、招待状に次のような内線番号が含まれている必要があります。
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロールパネルを使用して、ユーザーの電話番号を構成します。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>ボイスメールに直接通話を送信するように設定する

ダイレクトルーティングを使うと、ユーザの通話を終了してユーザのボイスメールに直接送ることができます。 直接ボイスメールに通話を送信する場合は、符号化 = app: ボイスメールを要求 URI ヘッダーに接続します。 たとえば、"sip: user@yourdomain、不透明 = アプリ: ボイスメール" です。 この場合、Teams ユーザーは呼び出し通知を受信しません。通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Microsoft Teams で通話を確実に行うためにチームのみのモードをユーザーに割り当てる

直接ルーティングを使うには、チームクライアントで着信通話を確実にするために、ユーザーが Teams 専用モードになっている必要があります。 ユーザーをチームのみのモードに配置するには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。 詳細については、「 [IT 管理者向けのアップグレードガイダンス](upgrade-to-teams-on-prem-overview.md)」を参照してください。 組織で Skype for Business Server または Skype for Business Online を使用している場合は、skype と Teams の相互運用性については、次の記事を参照してください。 [skype For business との移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
