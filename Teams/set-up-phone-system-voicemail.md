---
title: クラウド ボイスメールのセットアップ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: ユーザーのアカウントをクラウド ボイスメールする方法について学習します。
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974474"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、ユーザー Microsoft 365アカウントを設定する管理者クラウド ボイスメール向けです。 

クラウド ボイスメールのメールボックスにボイスメール メッセージをExchangeします。 クラウド ボイスメールサード パーティのメール システムはサポートされていません。 ライセンスExchange Online要件については、「サービスの説明[Exchange Online参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)。 管理者ロールの詳細については、「管理者ロールについて [」を参照してください](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="cloud-voicemail-provisioning"></a>クラウド ボイスメールプロビジョニング

ユーザー Teams、クラウド ボイスメール自動的に設定およびプロビジョニングされます。 *ライセンスMicrosoft Teams 電話ライセンスは必要クラウド ボイスメール。*

ユーザーのプロビジョニングTeamsオンライン ユーザーの場合と同じSkype for Businessではありません。 Skype for Business Online ユーザーの場合、クラウド ボイスメール はユーザーに 電話システム ライセンスが割り当てられたときに自動的に設定され、プロビジョニング システムによって有効エンタープライズ VoIPプロビジョニングされました。

オンプレミスSkype for Business Serverユーザーの場合、クラウド ボイスメールは自動的に設定およびプロビジョニングされます。 ただし、呼び出しをルーティングする Skype for Business Server環境を構成する必要クラウド ボイスメール。 詳細については、「オンプレミス ユーザー向[クラウド ボイスメールサービスの計画」を参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail.md)。 

## <a name="cloud-voicemail-storage"></a>クラウド ボイスメール ストレージ

クラウド ボイスメールによって生成されたボイスメール メッセージは、ユーザーの Exchange メールボックスに配信され、Exchange Online または Exchange Server に保存されます。 ボイスメール用の特定のストレージや追加のストレージはありません。 ボイスメールにアクセスするクライアント (Microsoft Outlook、Microsoft Teams、Skype for Business など) は、Exchange メールボックスと提供された API を介して行います。 

ボイスメール メッセージには、音声メッセージとボイスメールの文字起こしを含む添付オーディオ ファイルが含まれます (有効な場合)。 

ユーザー Exchangeのメールボックスには、任意のカスタム記録されたあいさつメッセージが格納されます。 これらのあいさつメッセージは、着信クラウド ボイスメールに必要に応じて応答によって取得されます。 

## <a name="cloud-voicemail-processing"></a>クラウド ボイスメール処理 

通話の記録と文字起こしクラウド ボイスメール、Microsoft 365にルーティングされる呼び出しの起点から始クラウド ボイスメール。 その後、メッセージはユーザーのメールボックスExchangeされます。 

たとえば、ヨーロッパのセッション ボーダー コントローラー (SBC) を介して使用できないダイレクト ルーティング ユーザーに通話が入った場合、ボイスメールの録音とトランスクリプションはヨーロッパで行われます。 その後、メッセージはユーザーのメールボックスExchangeされます。 別の例として、北米のTeamsユーザーが、ヨーロッパで使用できないユーザー Teamsを呼び出したとします。 この場合、通話は北米で開始され、処理は北米で行われます。その後、ボイスメールはヨーロッパのユーザーの Exchange に配信されます。 

メールボックスへのボイスメールの配信Exchange、他の電子メールと同様に、簡易メール転送プロトコル (SMTP) を使用して行われます。 

## <a name="manage-cloud-voicemail-for-users"></a>ユーザークラウド ボイスメールを管理する 

ユーザーのクラウド ボイスメール機能を管理するには、次Teams PowerShell モジュールを使用します。 

ユーザー グループクラウド ボイスメール機能を管理するには、[New-CsOnlineVoicemailPolicy コマンドレットを使用](/powershell/module/skype/new-csonlinevoicemailpolicy)します。 通話応答ルール、ボイスメールトランスクリプション、トランスクリプション不適切なマスク、文字起こし翻訳、システム プロンプト言語などの機能に対して、既存または新規のボイスメール ポリシーを構成して割り当てできます。 詳細については、「 [New-CsOnlineVoicemailPolicy」を参照してください](/powershell/module/skype/new-csonlinevoicemailpolicy)。

個々のクラウド ボイスメール設定を管理するには、[Set-CsOnlineVoicemailUserSettings コマンドレットを使用](/powershell/module/skype/set-csonlinevoicemailusersettings)します。 クラウド ボイスメールに適用できる設定には、通話応答ルール、プロンプト言語、既定のテキスト読み上げ、休暇のあいさつ文が含まれます。 詳細については、「 [Set-CsOnlineVoicemailUserSettings」を参照してください](/powershell/module/skype/set-csonlinevoicemailusersettings)。
(エンド ユーザーは、[**CallsConfigure** ->  ボイスメール] に移動して、Teams クライアントでこれらの設定 **設定** -> **構成** することもできます)。

[Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) コマンドレットを使用し、VoicemailEnabled パラメーターを $false に設定することで、ユーザーの クラウド ボイスメール を無効にすることもできます。 この設定により、ユーザークラウド ボイスメールボイスメールを記録できなくなりました。



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>呼び出しのルーティングを制御クラウド ボイスメール 

クラウド ボイスメール に対してプロビジョニングされたすべてのユーザーの既定の設定は、クラウド ボイスメール への呼び出しのルーティングを許可し、ユーザーが通話を クラウド ボイスメール に転送できる設定です。 

allowVoicemail パラメーターで Set-CsTeamsCallingPolicy コマンドレットを使用して、クラウド ボイスメール への呼び出しのルーティングを Teams ユーザーに許可するかどうかを制御できます。 詳細については、「 [Set-CsTeamsCallingPolicy」を参照してください](/powershell/module/skype/set-csteamscallingpolicy.md)。 

- AllowVoicemail を AlwaysDisabled に設定した場合、ユーザーの着信転送または未応答の設定に関係なく、通話はボイスメールにルーティングされません。 ボイスメールは、通話の転送または未応答の設定として、Teams。  

- AllowVoicemail を AlwaysEnabled に設定した場合、ユーザーの未応答の着信転送設定に関係なく、通話は 30 秒間呼び出された後、応答しないボイスメールに常に転送されます。  

- AllowVoicemail を UserOverride に設定した場合、通話はユーザーの着信の転送や未応答の設定に基づいてボイスメールに転送されます。 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>オンプレミス ユーザークラウド ボイスメールを使用するアカウントを設定する

クラウド ボイスメール を使用すると、Exchange サーバーにメールボックスを持つユーザー、または Skype for Business Server を使用しているユーザーにボイス メール機能を提供できます。 

このセクションでは、メールボックス ユーザーに対してクラウド ボイスメール設定Exchange Serverについて説明します。 ユーザーのユーザーに対して クラウド ボイスメールをSkype for Business Serverについては、「オンプレミス ユーザー向クラウド ボイスメールサービスを計画する」[を参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>メールボックス ユーザークラウド ボイスメールのExchange Server設定する

次の情報は、メールボックスを持つクラウド ボイスメールユーザーとTeamsを使用するための構成についてExchange Server。

1. ボイスメール メッセージは、ユーザーのメールボックスに配信され、Exchange経由でルーティングされた SMTP 経由Exchange Online Protection。 これらのメッセージの配信を正常に行う場合は、Exchange サーバーとサーバー間で Exchange コネクタが正しく構成Exchange確認Exchange Online Protection。 詳細については、「コネクタを使用[してメール アドレスを構成する」をFlow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

2. Teams クライアントであいさつ応答メッセージやビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 と Exchange Server メールボックスの間の接続を設定する必要があります。 この接続を有効にするには、「Exchange 組織と Exchange Online 組織間の [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。 また、「Configure [Integration and OAuth between](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) Teams and Exchange Server」で説明されている Teams と Exchange Server の間で統合と OAuth を構成Teams必要Exchange Server。


## <a name="enable-protected-voicemail-in-your-organization"></a>組織内で保護されたボイスメールを有効にする

組織内のユーザーのボイスメール メッセージを他のユーザーが離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。 メール フロー ルールを使用してメッセージの暗号化を適用すると、これらのボイスメール メッセージが他の受信者に転送されるのを防ぐことが可能です。 保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスに通話するか、Android または iOS の Outlook、Outlook on the web、または Outlook でメッセージを開いて、保護されたボイスメール メッセージをリッスンできます。 保護されたボイスメール メッセージは、Skype for BusinessまたはMicrosoft Teams。

メッセージの暗号化の詳細については、「メール メッセージを暗号化 [するメール フロー ルールを定義する」を参照してください](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>ユーザーが他の機能についてクラウド ボイスメールする

ユーザーが新しい機能を使用および管理する方法についてクラウド ボイスメール、次の記事をお勧めします。 

- [Teams でボイスメールを確認Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [通話設定を Teams管理する](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
