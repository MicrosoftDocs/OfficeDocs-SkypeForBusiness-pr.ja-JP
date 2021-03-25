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
description: 'Skype for Business をインストールするために組織のドメイン、ユーザー、IM、プレゼンスを設定する方法について学習します。 また、電話会議、電話システムと通話プラン、Skype 会議ブロードキャストを設定する方法も参照してください。 '
ms.openlocfilehash: 0c357c1dbe5b91c06b385562bf31d5f1307bd240
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109963"
---
# <a name="set-up-skype-for-business-online"></a>Skype for Business Online をセットアップする

Skype for Business をセットアップするには、グローバル管理者権限が必要です。 Web の一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は [、Skype](https://go.microsoft.com/fwlink/?linkid=391089) for Business をセットアップするために Microsoft パートナーを採用する方法を検討してください。

## <a name="setting-up-skype"></a>Skype のセットアップ

Microsoft 365 または Office 365 サブスクリプションを使用して Skype をセットアップする方法をご覧ください。 この記事の手順に従って、セットアップを完了できます。

## <a name="1-plan-for-skype-for-business"></a>1. Skype for Business のプラン

**[Microsoft 365 Business Premium Standard](https://products.office.com/business/office-365-business-premium)** または Business **Essentials** をお持ちである場合は、Skype for Business を使用して、サブスクリプションを利用している他のユーザーにオンライン通話を行います。 たとえば、ビジネスに 10 人のユーザーがいて、IM 会議やオンライン会議で [Skype for Business](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) を使い始め、Skype for [Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) を使った会議は、以下の手順 2 ~ 6 を実行した後で開始できます。 また [、Outlook で Skype for Business 会議をオンライン](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) 会議に設定できます。

Skype for Business を使用して、社外のユーザーとの通話の送受信 *を* 行う場合:

- **オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。 小規模な企業 (1 ~ 2 人など) の場合は、Skype アプリを使う方が良い方法です。 国内通話と国際通話で利用する場合は、より安価な手段となります。 電話会議を開催し、ビデオ通話を行い、プレゼンテーション用にデスクトップを共有することができます。 [料金と支払オプションを確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。

- **オプション 2。プランをアップグレードし、365** 用の電話システムと通話Officeします。 このコストを確認し、切り替える最も簡単な方法は、ビジネス製品のサポートへのお問い合わせ [-](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 管理者向けヘルプを使用して、すべてを実行させる方法です。

詳細については、「一Office [365 のセットアップを計画する」を参照してください](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)。

## <a name="2-sign-in-to-office-365"></a>2. Office 365 にサインインする
<a name="bkmk_signin"> </a>

Skype for Business Online は、365 Officeサービスの一部です。 Skype for Business Online をセットアップするには、365 から Officeする必要があります。 この操作を行うには、次の操作を行います。

1. Microsoft 365 または Office 365 のユーザー ID を見<em>rob@fourthcoffee.com。</em> Skype for Business Online の購入時に作成した Microsoft 365 または Office 365 ユーザー ID を含むメールを Microsoft Online Services チームから受け取った。 メールは次のように表示されます。

    ![Skype for Business Online にサインアップした後に受信したウェルカム メールの例。 Microsoft 365 または 365 Office ID が含まれている。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. 管理センターに [サインインし](https://admin.microsoft.com) 、Microsoft 365 または Office 365 のユーザー ID とパスワードを入力します。 

## <a name="3-set-up-your-domain-and-users"></a>3. ドメインとユーザーをセットアップする
<a name="bkmk_users"> </a>

Office 365 にサインインしたので、Skype for Business Online を使用するドメインと組織内のユーザーを設定できます。

1. [Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)にドメインとユーザーを追加する: Office 365 セットアップ ウィザードを使用して、fourthcoffee.com 365 でカスタム ドメイン *(fourthcoffee.com* など) をセットアップOfficeします。 **既定では、Office 365 セットアップ ウィザードには、Skype for Business Online のセットアップと Skype for Business ユーザー ID の作成が含まれます。** ウィザードを使用して Office 365 のドメインをセットアップした場合は、この手順を完了します。

2. [ドメインと DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0)接続を確認する: ドメインのトラブルシューティング ツールであるツールを使用して、ドメインと DNS の設定が正しいか確認します。 今後の問題のソースとして DNS 設定を排除できるので、この作業は後でセットアップの問題を把握する上で大きな助けになります。

3. [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO)と IP アドレス範囲を使用する: ほとんどの中小企業は、この手順を実行する必要があります。 **ただし、Web の** 一部へのアクセスを制限するファイアウォールまたはプロキシ サーバーがある場合は、Skype for Business Online エンドポイントへのアクセスを許可するルールを作成する必要があります。 これは、ファイアウォールとプロキシ サーバーの構成経験があるユーザーが実行する高度な手順です。 以前にこの設定を行ったことが見当たらない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーに Skype for Business のセットアップを採用する方法を検討してください。

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. 組織内で IM とプレゼンスを設定する
<a name="bkmk_IM"> </a>

インスタント メッセージング (IM) とプレゼンス[(Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)のプレゼンス情報へのアクセスを制御する) は、Skype for Business に含まれる基本的な機能です。 既定では、お客様のビジネスのユーザーは、互いに Skype と IM を使用できます。

1. **Skype for Business ユーザーが通信できる他のユーザーを選択します。**

   - [ユーザーが外部の Skype for Business ユーザーと連絡を取り合うのを許可する](allow-users-to-contact-external-skype-for-business-users.md) お客様と *他*  の企業の両方がシステムを構成する必要があります。

     **重要**: rob@contosowest.com と ina@contosoeast.com など、ビジネスに 2 つのドメインがある場合は、すべてのユーザーが互いに通信できるよう、この手順を実行する必要があります。

   - [Skype for Business ユーザーが社外の Skype 連絡先を](let-skype-for-business-users-add-skype-contacts.md) 追加する

2. **同僚がオンラインかどうかを確認するユーザーを選択します。** プレゼンス機能では、オンライン状態のユーザーと空き時間情報 (空き時間情報、取り込み中、離れた場所、発表中など) が表示されます。

    ![個人メッセージを含むユーザーのオンライン状態の例。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    ビジネスのすべてのユーザーに対して既定の設定を選択できます。

   - 組織内のすべてのユーザーにユーザーのオンライン プレゼンスを自動的に表示する

   - ユーザーのオンライン プレゼンスを連絡先にのみ表示する

手順については [、「Skype for Business Online でプレゼンスを構成する」を参照してください](configure-presence-in-skype-for-business-online.md)。

## <a name="5-download-and-install-skype-for-business"></a>5. Skype for Business をダウンロードしてインストールする
<a name="bkmk_download"> </a>

お使いの PC、Mac、またはモバイル デバイスで Skype for Business を使用するには、お客様と他のユーザーが最初に Skype for Business ダウンロードをデバイスにインストールする必要があります。

- [Skype for Business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)する: Microsoft 365 管理センターからアプリをダウンロードして、PC または Mac にインストールする方法について説明します。

- [Office 365](deploy-the-skype-for-business-client-in-office-365.md)で Skype for Business クライアントを展開する: 大企業にアプリを展開する手順。

- [Skype for Business のインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Android デバイス、iOS デバイス、Windows Phone で Skype for Business をダウンロード、インストール、サインインします。

- [携帯電話の](turn-on-or-off-mobile-phone-notifications.md)通知のオンとオフを切り替えます: モバイル デバイスに Skype for Business がインストールされている場合、自分と他のユーザーが受信したインスタント メッセージと見逃したインスタント メッセージに関する通知を受信できます。

## <a name="6-test-to-make-sure-everything-is-working"></a>6. すべての機能が動作しているテストを行う
<a name="bkmk_test"> </a>

まず、自分と他のユーザーがビデオ: Skype for Business にサインインおよびサインアウトできるかどうか [をテストします](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)。 IM で互いに IM をやり取りし、互いにプレゼンスを確認し、簡単な会議を試す。

問題がある場合 以下の操作を行います。

- [Skype for Business へのサインインでヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) サインインに関する一般的な問題について確認してください。

- [ビジネス製品のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。 お手伝いします!

## <a name="do-you-want-to-set-up-other-available-features"></a>その他の利用可能な機能を設定しますか?
<a name="bkmk_more"> </a>

その他の機能を設定する前に、その機能のライセンスを持っている必要があります。 [Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>電話会議をセットアップする

組織内のユーザーは電話を使って会議に参加する必要が生じることがあります。 Skype for Business には、このような状況専用の電話会議機能が含まれています。 参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Office 365 で電話システムと通話プランをセットアップする

Office 365 の電話システム機能は、業務用の電話システムを提供します。 組織内の他の Skype for Business ユーザーへの通話は無料で、従業員は互いにボイスメールを受け取り、外部の発信者も受け取ります。 電話システムでは次の機能を利用できます。

通話プラン サービスを追加すると、従業員は Skype for Business の主要電話番号を取得します。 社外からの電話の送受信が可能です。 VoIP 電話、PC、モバイル デバイス間で音声通話を行えます。 また、緊急時に 911 に電話でサポートを受け取る場合があります。

詳しいセットアップ手順については、「通話プランをセットアップする」を参照してください。

### <a name="set-up-skype-meeting-broadcast"></a>Skype 会議ブロードキャストをセットアップする

Skype 会議ブロードキャストは、最大 10,000 人の出席者を含む会議を作成、ホスト、ブロードキャストできる機能です。 **機能の詳細については、「Skype 会議ブロードキャストとは [」を参照してください。](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

Skype 会議ブロードキャストをセットアップする手順の概要を次に示します。

1. [Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)のライセンスの割り当てまたは削除: ブロードキャスト会議を開催する予定のユーザー全員に Skype for **Business Online** または **エンタープライズ** プランのライセンスを割り当てる。

2. [Skype 会議ブロードキャストを有効](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md)にする: 既定では、この機能は有効になっていません。 有効にした後、ユーザーは組織内の他のユーザーとのブロードキャスト会議を開催できます。

3. [Skype 会議ブロードキャスト](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)用にネットワークをセットアップする: 組織外の出席者とウェビナーや他のブロードキャストを開催する場合は、ネットワークを構成する必要があります。

4. [Skype 会議ブロードキャストを](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) スケジュールし [、Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)会議ブロードキャストに参加する: Skype 会議ブロードキャストをスケジュールして、他のユーザーが会議に参加しようとして、ブロードキャスト会議が機能します  *https://portal.broadcast.skype.com*  。

## <a name="learn-about-network-connectivity-requirements"></a>ネットワーク接続の要件について
<a name="bkmk_more"> </a>

Skype for Business でのオーディオ、ビデオ、アプリケーション共有の品質は、エンドツーエンドのネットワーク接続の品質に大きく影響されます。 最適なエクスペリエンスを得る場合は、会社のネットワークと Skype for Business Online の間に高品質の接続を確立することが重要です。 ネットワークとチューニングに関する情報については、「Skype for Business Online のパフォーマンス [をチューニングする」を参照してください](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)。

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>セットアップが完了しましたか? Skype for Business の使用を開始する
<a name="bkmk_more"> </a>

[Skype for Business のトレーニング](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): すぐに始めるのに役立つトレーニング トピックの一覧をご覧ください。

[Skype for Business 電話会議を開始する](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Skype for Business のビデオ デバイス オプションを設定する](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Skype for Business を使用してビデオ通話を送受信する](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>関連項目
<a name="bkmk_more"> </a>

[Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)