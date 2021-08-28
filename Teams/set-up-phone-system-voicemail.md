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
description: 'ユーザーに対してクラウド ボイスメール設定する方法について学習します。 '
ms.openlocfilehash: c9e073a61501143c478d78b9184602f4eebe9264
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590731"
---
# <a name="set-up-cloud-voicemail"></a>クラウド ボイスメールのセットアップ

この記事は、Microsoft 365 または Office 365 管理者向けです。「一[](/microsoft-365/admin/add-users/about-admin-roles)部のユーザーに対して クラウド ボイスメール 機能を設定する管理者ロールについて」を参照してください。

> [!NOTE]
> クラウド ボイスメールは、ボイスメール メッセージの受信を Exchange メールボックスにのみサポートし、サード パーティのメール システムをサポートしません。 

> [!NOTE]
> 代理人が委任者の代わりに通話に応答すると、その代理人の通知クラウド ボイスメール。 ユーザーは、着信を見逃した場合に通知を受け取る可能性があります。

## <a name="cloud-voicemail-for-teams-users"></a>クラウド ボイスメールユーザー Teamsする

ユーザー Teams、クラウド ボイスメール自動的に設定およびプロビジョニングされます。 この場合、電話システムライセンスは必要クラウド ボイスメール。 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>メールボックス ユーザークラウド ボイスメールのExchange Server設定する

次の情報は、オンラインのユーザークラウド ボイスメールがメールボックスを持っているユーザーと一緒に作業電話システムを構成する方法Exchange Server。 
  
1. ボイスメール メッセージは、ユーザーのメールボックスに配信されExchange経由でルーティングされた SMTP 経由でExchange Online Protection。 これらのメッセージの正常な配信を有効にするには、Exchange コネクタがサーバーとサーバー間で正Exchange構成されていることをExchange Online Protection。[コネクタを使用してメール アドレスを構成Flow。](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 

2. Skype for Business クライアントであいさつ応答メッセージやビジュアル ボイスメールのカスタマイズなどのボイスメール機能を有効にするには、Microsoft 365 または Office 365 から Exchange Web サービスを介した Exchange サーバー メールボックスへの接続が必要です。 この接続を有効にするには、「Exchange 組織と Exchange Online 組織間の[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)認証の構成」で説明されている新しい Exchange Oauth 認証プロトコルを構成するか、Exchange 2013 CU5 以上から Exchange ハイブリッド ウィザードを実行する必要があります。 さらに、Skype for Business Online と Exchange Online と Exchange Server の間の統合と OAuth の構成に関するページで説明されている Skype for Business Online と Exchange サーバーの間で統合と[Oauth を構成する必要Exchange Server。](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>ユーザーのクラウド ボイスメール設定Skype for Business Serverする

サーバー ユーザー Skype for Businessを構成クラウド ボイスメール、オンプレミス ユーザーの クラウド ボイスメール サービスの計画[に関するページを参照してください](/skypeforbusiness/hybrid/plan-cloud-voicemail)。

## <a name="enabling-protected-voicemail-in-your-organization"></a>組織内で保護されたボイスメールを有効にする

組織内のユーザーのボイスメール メッセージを他のユーザーが離れる場合、ボイスメールはメール メッセージの添付ファイルとしてユーザーのメールボックスに配信されます。 メール フロー ルールを使用してメッセージの暗号化を適用すると、これらのボイスメール メッセージが他の受信者に転送されるのを防ぐことが可能です。 保護されたボイスメールを有効にした場合、ユーザーは、ボイスメール メールボックスを呼び出したり、Android または iOS の Outlook、Outlook on the web、または Outlook でメッセージを開いて、保護されたボイスメール メッセージをリッスンできます。 保護されたボイスメール メッセージは、Skype for BusinessまたはMicrosoft Teams。

メッセージの暗号化の詳細については、「電子メールの暗号化」 [を参照してください](/microsoft-365/compliance/email-encryption?view=o365-worldwide)。

保護されたボイスメールを設定するには、次の操作を行います。

1. グローバル管理者 https://admin.microsoft.com アクセス許可を持つアカウントを使用して に移動し、サインインします。
2. [すべて **表示] を** 選択し、[管理センター]**に移動**  >  **Exchange。**
3. [管理センター Exchangeで、[メール フロールール **] を**  >  **選択します**。
4. [追加 **+** **]** を選択し、[**メッセージにOffice 365 Message Encryption保護を適用する] を選択します**。
5. 新しいメール フロー ルールの名前を指定し、[このルールを適用する場合] で、[メッセージのプロパティにメッセージの種類を含める] [ボイス メール]  >    >  **を選択します**。 **[OK] を選択します**。
6. [**次の操作を行う**] で **、[Office 365 Message Encryption保護と** 権限保護をメッセージに適用する] を選択し、[1 つ選択]**を選択します**。 [RMS **テンプレート] で、[** 転送しない **] を選択します**。 **[OK] を選択** し、[保存]**を選択します**。
    > [!NOTE]
    > RMS テンプレート **の一覧が** 空の場合は、Message Encryption を設定する必要があります。 Message Encryption の設定の詳細については、次の記事を参照してください。
    > - [新しい Message Encryption 機能を設定する](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Azure Information Protection のテンプレートの構成と管理](/information-protection/deploy-use/configure-policy-templates)
    > - [メールの [転送しない] オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a>ユーザーがボイスメール機能をTeamsする

ボイスメール設定の管理に関するユーザー向け情報と、その他の通話機能については、以下Teams。

- [で通話設定を管理Teams。](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) この記事では、すべてのエンド ユーザーと通話機能を管理Teams説明します。 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Skype for Business ボイスメールの機能に関するユーザーの理解を支援する

ユーザーが Skype for Business ボイスメールを正しく使用できるように支援するためのトレーニング情報と記事が用意されています。以下の記事をユーザーに紹介してください。

- [Skype for Business ボイス メールの確認とオプション](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): この記事では、Skype for Business でボイスメールを再生し、ボイスメール応答メッセージを変更し、ボイスメールの設定を変更し、ボイスメールを異なる速度で再生する方法について説明します。

- [Skype for Business 2016 トレーニング](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[電話システムで利用できる機能](here-s-what-you-get-with-phone-system.md)

[Skype for Business Server と Exchange Server の移行の計画](/SkypeForBusiness/hybrid/plan-um-migration)
