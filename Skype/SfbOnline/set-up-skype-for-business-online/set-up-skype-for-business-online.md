---
title: Skype for Business Online をセットアップする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- Alchemy
- LIL_Placement
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
description: '組織のドメイン、ユーザー、IM、プレゼンスをセットアップして、組織がドメインをインストールSkype for Business。 また、電話会議、通話プランと通話プラン電話システム会議ブロードキャストを設定するSkypeを参照してください。 '
ms.openlocfilehash: fcca1a3181ca0f5753fd53811290d710e8030064
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239809"
---
# <a name="set-up-skype-for-business-online"></a>Skype for Business Online をセットアップする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

アカウントを設定するには、グローバル管理者のアクセス許可がSkype for Business。 Web の一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は[、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーに問い合Skype for Businessを検討してください。

## <a name="setting-up-skype"></a>設定Skype

サブスクリプションまたはサブスクリプションを使用してSkypeを設定Microsoft 365必要Office 365します。 この記事の手順に従って、セットアップを完了できます。

## <a name="1-plan-for-skype-for-business"></a>1. プランのSkype for Business

Standard または **Business Essentials** **[Microsoft 365 Business Premiumを](https://products.office.com/business/office-365-business-premium)** 使用している場合は、Skype for Business を使用して、サブスクリプションを利用している企業内の他のユーザーにオンライン通話を行います。 たとえば、ビジネスに 10 人の人がいて[、IM](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)会議とオンライン会議に Skype for Business を使い始め、次の手順 2 から 6 を実行した後に Skype for Business を使用して[Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)で会議を開始できます。 また、[オンライン会議Skype for Business会議Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)会議を設定できます。

このサービスを使用してSkype for Business外部のユーザーとの通話を送受信する場合は、次 *の方法を* 実行します。

- **オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。 小規模な企業 (1 ~ 2 人など) がある場合は、Skype アプリを使用する方が便利です。 国内通話と国際通話で利用する場合は、より安価な手段となります。 電話会議を開催し、ビデオ通話を行い、プレゼンテーション用にデスクトップを共有することができます。 [料金と支払オプションを確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。

- **オプション 2.プランをアップグレードし、プランと 電話システム 通話プランを購入Office 365。** このコストを確認し、切り替える最も簡単な方法は、ビジネス製品のサポートに問い合わせ [- 管理者](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 向けヘルプを使用して、すべての操作を行う方法です。

詳細については、「一Office 365[のセットアップを計画する」を参照してください](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。

## <a name="2-sign-in-to-office-365"></a>2. サインインして Office 365
<a name="bkmk_signin"> </a>

Skype for Businessオンラインは、サービスのOffice 365の一部です。 Skype for Business Online を設定するには、アカウントにサインインOffice 365。 その方法を次に示します。

1. ユーザー ID Microsoft 365またはOffice 365を見つける (例: <em>rob@fourthcoffee.com)。</em> Microsoft Online Services Online の購入時に作成した Microsoft 365 または Office 365 ユーザー ID を含むメールが Skype for Business されました。 メールは次のように表示されます。

    ![Skype for Business Online にサインアップした後に受信したウェルカム メールの例。 このファイルには、ユーザー Microsoft 365またはOffice 365 ID が含まれている。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 管理センターに[サインインし、](https://admin.microsoft.com)ユーザー ID とパスワードMicrosoft 365またはOffice 365を入力します。 

## <a name="3-set-up-your-domain-and-users"></a>3. ドメインとユーザーを設定する
<a name="bkmk_users"> </a>

Office 365 にサインインすると、ドメインと組織内のユーザーが Skype for Business Online を使用Skype for Businessできます。

1. [ドメインとユーザー](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)を Office 365 に追加する: Office 365 セットアップ ウィザードを使用して、カスタム ドメイン (fourthcoffee.com *など)* を Office 365 で設定します。 **既定では、Office 365 セットアップ ウィザードには、Skype for Business Online のセットアップとユーザー ID Skype for Businessが含まれています。** 既にウィザードを使用してドメインをセットアップしている場合はOffice 365、この手順は完了しています。

2. [ドメインと DNS 接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): ドメインのトラブルシューティング ツールを使用して、ドメインと DNS の設定が正しいか確認します。 今後の問題のソースとして DNS 設定を排除できるので、セットアップの問題を後で把握するには、この作業が長い道のりになります。

3. [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)と IP アドレス範囲: ほとんどの小規模企業は、この手順を実行する必要があります。 **ただし、Web の一** 部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は、Skype for Business Online エンドポイントへのアクセスを許可するルールを作成する必要があります。 これは、ファイアウォールとプロキシ サーバーの構成経験のあるユーザーが実行する高度な手順です。 この設定をまだ行ったことがない場合は[、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089)パートナーを採用してユーザーにSkype for Businessを検討してください。

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 組織内で IM とプレゼンスを設定する
<a name="bkmk_IM"> </a>

インスタント メッセージング (IM) とプレゼンス ( Skype for Business でのプレゼンス[情報](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)へのアクセスの制御) は、Skype for Business に含まれている基本的な機能です。 既定では、ビジネスのユーザーは、Skype IM を使用できます。

1. **ユーザーが通信できる他Skype for Businessを選択します。**

   - [ユーザーが外部ユーザーに連絡Skype for Business許可する](allow-users-to-contact-external-skype-for-business-users.md)自分と *他のビジネス* の両方が、システムを構成する必要があります。

     **重要**: rob@contosowest.com と ina@contosoeast.com など、ビジネスに 2 つのドメインがある場合は、すべてのユーザーが相互に通信できるよう、この手順を実行する必要があります。

   - [ユーザーがSkype for Business外部のSkypeを追加](let-skype-for-business-users-add-skype-contacts.md)する

2. **同僚がオンラインかどうかを確認するユーザーを選択します。** プレゼンス機能では、オンラインのユーザーと、空き時間情報、取り込み中、空き時間情報、発表中など、そのユーザーの空き時間情報が表示されます。

    ![個人のメッセージを含むユーザーのオンライン状態の例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    ビジネスのすべてのユーザーの既定の設定を選択できます。

   - 組織内のすべてのユーザーにユーザーのオンライン プレゼンスを自動的に表示する

   - 連絡先にのみユーザーのオンライン プレゼンスを表示する

手順については、「Skype for Business Online でのプレゼンス[の構成」を参照してください](configure-presence-in-skype-for-business-online.md)。

## <a name="5-download-and-install-skype-for-business"></a>5. ダウンロードしてインストールSkype for Business
<a name="bkmk_download"> </a>

PC Skype for Business Mac、またはモバイル デバイスでアプリを使用するには、ユーザーと他のユーザーが最初にデバイスに Skype for Business をインストールする必要があります。

- [インストールSkype for Business:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Microsoft 365 管理センターからアプリをダウンロードし、PC または Mac にインストールする方法について説明します。

- [大規模なSkype for Businessにアプリ](deploy-the-skype-for-business-client-in-office-365.md)Office 365デプロイする手順に関するページで、クライアントをデプロイします。

- [インストールSkype for Business:](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)Android デバイス、iOS デバイス、およびスマートフォンSkype for Businessにダウンロード、インストール、サインインWindowsします。

- [携帯電話の通知](turn-on-or-off-mobile-phone-notifications.md)をオンまたはオフにする: モバイル デバイスに Skype for Business をインストールすると、受信したインスタント メッセージと見逃したインスタント メッセージに関する通知を受信できます。

## <a name="6-test-to-make-sure-everything-is-working"></a>6. テストして、すべてが動作している
<a name="bkmk_test"> </a>

まず、自分とビジネスの他のユーザーがビデオ: サインインとサインアウトを実行できるかどうか[をテスト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)Skype for Business。 互いに IM を取り合い、互いにプレゼンスを確認し、簡単な会議を試みる。

問題がある場合 以下の操作を行います。

- [サインインに関するヘルプがSkype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)サインインに関する一般的な問題の一部です。

- [ビジネス製品のサポートに問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。 お手伝いします。

## <a name="do-you-want-to-set-up-other-available-features"></a>その他の利用可能な機能を設定しますか?
<a name="bkmk_more"> </a>

その他の機能を設定する前に、その機能のライセンスを持っている必要があります。 [Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>電話会議をセットアップする

組織内のユーザーは電話を使って会議に参加する必要が生じることがあります。 Skype for Business、この状況だけの電話会議機能が含まれています。 参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>通話プラン電話システム通話プランを設定Office 365

この電話システム機能Office 365、ビジネス用の電話システムを提供します。 組織内のユーザー Skype for Business他のユーザーへの呼び出しは無料で、従業員は互いにボイスメールを受け取り、外部の発信者を受け取る可能性があります。 次に示すのは、電話システム。

通話プラン サービスを追加すると、従業員は通話プランにプライマリ電話番号Skype for Business。 外部のユーザーは、業務外で電話を行い、受信できます。 VoIP 電話、PC、モバイル デバイス間で音声通話を行えます。 また、緊急対応の場合は、911 に電話してサポートを受け取る必要があります。

詳細なセットアップ手順については、「通話プランを設定する」を参照してください。

### <a name="set-up-skype-meeting-broadcast"></a>会議ブロードキャストSkype設定する

Skype会議ブロードキャストは、最大 10,000 人の出席者を含む会議を作成、ホスト、およびブロードキャストできる機能です。 **機能の詳細については、「会議ブロードキャストの概要 [」Skypeしてください。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

会議ブロードキャストを設定する手順の概要をSkypeします。

1. [一Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)のライセンスの割り当てまたは削除: ブロードキャスト会議を開催する全員に **Skype for Business Online** または **Enterprise プラン** ライセンスを割り当てる。

2. [会議Skype有効](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)にする: 既定では、この機能は有効になっていません。 有効にした後、ユーザーは組織内の他のユーザーとのブロードキャスト会議をホストできます。

3. [Skype 会議](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)ブロードキャスト用にネットワークを設定する: 組織外の出席者とウェビナーや他のブロードキャストをホストする場合は、ネットワークを構成する必要があります。

4. [](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) Skype 会議ブロードキャストをスケジュールし [、Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)会議ブロードキャストに参加する : Skype 会議ブロードキャストをスケジュール設定し、他のユーザーに会議への参加を試みて、ブロードキャスト会議が機能します。 *https://portal.broadcast.skype.com*

## <a name="learn-about-network-connectivity-requirements"></a>ネットワーク接続の要件について学習する
<a name="bkmk_more"> </a>

Skype for Business でのオーディオ、ビデオ、およびアプリケーション共有の品質は、エンドツーエンドのネットワーク接続の品質の影響を大きく受け取っています。 最適なエクスペリエンスを実現するには、会社のネットワークと Skype for Business Online の間に高品質の接続が確立Skype for Businessです。 ネットワークとチューニングの情報については、「Tune Skype for Business Online performance 」[を参照してください](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>セットアップが完了しましたか? Skype for Business の使用を開始する
<a name="bkmk_more"> </a>

[Skype for Businessトレーニング](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): すぐに始めるのに役立つトレーニング トピックの一覧をご覧ください。

[電話会議Skype for Business開始する](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[[ビデオ デバイス] オプションを [Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[ビデオ通話を行い、ビデオ通話を受信Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>関連項目
<a name="bkmk_more"> </a>

[Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
