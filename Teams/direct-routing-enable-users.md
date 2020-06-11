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
ms.openlocfilehash: 2ae485398cef1cef2444de07dcabc4bf3f949ad5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691373"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする

この記事では、ユーザーが電話システムのダイレクトルーティングを有効にする方法について説明します。  これは、次の手順の手順2で、直接ルーティングを構成します。

- 手順1 [SBC と Microsoft 電話システムを接続して接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順2ユーザーが直接ルーティング、音声、ボイスメールを使用できるようにする**(この記事)
- 手順3 [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順4。 [数値を別の形式に変換する](direct-routing-translate-numbers.md) 


直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。

ユーザーに対して直接ルーティングを有効にする準備ができたら、次の手順を実行します。 

1. Microsoft 365 または Office 365 でユーザーを作成し、電話システムのライセンスを割り当てます。 
2. ユーザーが Skype for Business Online に所属していることを確認します。 
3. 電話番号を構成し、エンタープライズボイスとボイスメールを有効にします。 
4. チーム専用モードをユーザーに割り当てます。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成してライセンスを割り当てる 

Microsoft 365 または Office 365 で新規ユーザーを作成するには、2つのオプションがあります。 ただし、Microsoft は、ルーティングの問題を回避するためのオプションを組織で選ぶことをお勧めします。 

- オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。 「[オンプレミスディレクトリと Azure Active Directory の統合」を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)参照してください。
- Microsoft 365 管理センターで直接ユーザーを作成します。 「 [Microsoft 365 または Office 365 にユーザーを個別に、または一括して追加する」を](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)参照してください。 

Skype for business Online の展開 coexists が Skype for Business 2015 または Lync 2010 または2013オンプレミスの場合、サポートされているオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドに同期することだけです (オプション 1)。 

ライセンス要件の詳細については、「[プランダイレクトルーティング](direct-routing-plan.md)の[ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)」を参照してください。

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>ユーザーが Skype for Business Online に所属していることを確認する 

直接ルーティングを使用するには、ユーザーが Skype for Business Online を使用している必要があります。 RegistrarPool パラメーターを確認すると、infra.lync.com ドメインで値を指定する必要があります。

1. リモート PowerShell に接続します。
2. 次のコマンドを実行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>電話番号を設定し、エンタープライズボイスとボイスメールを有効にする 

ユーザーを作成してライセンスを割り当てたら、次の手順では、ユーザーの電話番号とボイスメールを構成します。 

電話番号を追加してボイスメールを有効にするには:
 
1. リモート PowerShell セッションに接続します。 
2. コマンドを入力します。 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    たとえば、"Spencer Low" というユーザーの電話番号を追加するには、次のように入力します。 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    使用される電話番号は、国コードを含む完全な電子電話番号として構成する必要があります。 

      > [!NOTE]
      > ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロールパネルを使用して、ユーザーの電話番号を構成します。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>ボイスメールに直接通話を送信するように設定する

ダイレクトルーティングを使うと、ユーザの通話を終了してユーザのボイスメールに直接送ることができます。 直接ボイスメールに通話を送信する場合は、符号化 = app: ボイスメールを要求 URI ヘッダーに接続します。 たとえば、"sip: user@yourdomain、不透明 = アプリ: ボイスメール" です。 この場合、Teams ユーザーは呼び出し通知を受信しません。通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Microsoft Teams で通話を確実に行うためにチームのみのモードをユーザーに割り当てる

直接ルーティングを使うには、チームクライアントで着信通話を確実にするために、ユーザーが Teams 専用モードになっている必要があります。 ユーザーをチームのみのモードに配置するには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。 詳細については、「 [IT 管理者向けのアップグレードガイダンス](upgrade-to-teams-on-prem-overview.md)」を参照してください。 組織で Skype for Business Server または Skype for Business Online を使用している場合は、skype と Teams の相互運用性については、次の記事を参照してください。 [skype For business との移行と相互運用性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
