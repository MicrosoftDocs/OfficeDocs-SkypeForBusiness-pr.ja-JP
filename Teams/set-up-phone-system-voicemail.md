---
title: クラウド ボイスメールのセットアップ
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
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
ms.openlocfilehash: f448ba79c2451383c0ca85916309bdfab3b69a96
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462371"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、Microsoft 365 または Office 365 管理者向けです。詳細については[](/microsoft-365/admin/add-users/about-admin-roles)、「クラウド ボイスメール 機能を設定する管理者ロールについて」を参照してください。 クラウド ボイスメール、ボイスExchangeを受信するユーザーのメールボックスを管理する必要があります。 サード パーティのメール システムはサポートされていません。

## <a name="cloud-voicemail-for-teams-users"></a>クラウド ボイスメールユーザー Teamsする

ユーザー Teams、クラウド ボイスメール自動的に設定およびプロビジョニングされます。 ライセンスMicrosoft Teams 電話ライセンスは必要クラウド ボイスメール。

## <a name="help-your-users-learn-teams-voicemail-features"></a>ユーザーがボイスメール機能をTeamsする

ボイスメールの使用と管理に関するユーザー向け情報は次Teams。

- [Teams でボイスメールを確認Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [[通話の設定を管理する] Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>オンプレミス ユーザークラウド ボイスメールを使用するアプリケーションの設定

クラウド ボイスメール を使用すると、Exchange サーバー上のメールボックスを持つユーザー、または Skype for Business Server を使用しているユーザーにボイス メール機能を提供できます。 このセクションでは、これらのシナリオについて説明します。 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>メールボックス ユーザークラウド ボイスメールのExchange Server設定

次の情報は、メールボックスを持クラウド ボイスメールを持つユーザーとMicrosoft Teams 電話を使用するための構成についてExchange Server。

1. ボイスメール メッセージは、ユーザーのメールボックスに配信されExchange経由でルーティングされた SMTP 経由でExchange Online Protection。 これらのメッセージの配信を正常に行う場合は、Exchange サーバーとサーバー間でコネクタが正しく構成Exchange確認Exchange Online Protection。[コネクタを使用してメール アドレスを構成Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. Skype for Business クライアントであいさつ応答メッセージやビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web サービスを介した Exchange サーバー メールボックスへの接続が必要です。 この接続を有効にするには、「Exchange 組織と Exchange Online 組織間の[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。 さらに、「Skype for Business Skype for Business Online と Exchange Server の間の統合と OAuth の構成」で説明されている Skype for Business Online と Exchange サーバー間の統合と Oauth を構成する[必要Exchange Server。](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>ユーザーのクラウド ボイスメール設定Skype for Business Serverする

サーバー ユーザーのSkype for Businessを構成するにはクラウド ボイスメールオンプレミス ユーザーの クラウド ボイスメール サービスの計画[に関するページを参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>組織内で保護されたボイスメールを有効にする

組織内のユーザーのボイスメール メッセージを他のユーザーが離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。 メール フロー ルールを使用してメッセージの暗号化を適用すると、これらのボイスメール メッセージが他の受信者に転送されるのを防ぐことが可能です。 保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスに通話するか、Android または iOS の Outlook、Outlook on the web、または Outlook でメッセージを開いて、保護されたボイスメール メッセージをリッスンできます。 保護されたボイスメール メッセージは、Skype for BusinessまたはMicrosoft Teams。

メッセージの暗号化の詳細については、「メール メッセージを暗号化するメール フロー [ルールを定義する」を参照してください](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。
