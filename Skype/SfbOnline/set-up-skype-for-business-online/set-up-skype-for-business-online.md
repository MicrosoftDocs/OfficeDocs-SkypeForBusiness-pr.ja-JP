---
title: "Skype for Business Online をセットアップします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: "Skype for Business をインストールするドメイン、ユーザー、IM と、組織のプレゼンスを設定する方法を学習します。電話会議、電話システムとプランの呼び出し] と Skype 会議メディアを設定する方法を参照してください。 "
ms.openlocfilehash: 45737ce4dc37fa8c5a85f55d4c32681f96a9bbf8
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-skype-for-business-online"></a>Skype for Business Online をセットアップします。
  
Skype for Business をセットアップする Office 365 グローバル管理者権限が必要です。Web パーツへのアクセス制限をファイアウォールまたはプロキシ サーバーがある場合は、する Skype for Business をセットアップする[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。
  
## <a name="setting-up-skype"></a>Skype のセットアップ

よう、Office 365 サブスクリプションでの Skype のセットアップのヘルプが必要です。セットアップを完了するには、この記事に示す手順を実行できます。
  
## <a name="1-plan-for-skype-for-business"></a>1. Skype for Business を計画します。

**[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)**または**Business Essentials**の場合は、サブスクリプションでのビジネスで他のユーザーに通話をオンラインに Skype for Business を使用することができます。たとえば、ビジネスの 10 個の連絡先ことができます[Skype for Business の IM およびオンライン会議の使用を開始](http://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd)すると[Skype for Business との会議](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851)が 2 ~ 6 の次の手順を実行した後に Skype for Business を使いします。. を[Skype for Business 会議を Outlook で設定](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)すると、オンライン会議を開催すぎます。
  
Skype for Business を使用して、作成し、ユーザーから*外部*ビジネスに**着信**を受信する場合は。
  
- **オプション 1 です。無料の[Skype アプリ](https://www.skype.com/)を使用して**します。非常に小規模企業 (たとえば、1 と 2 人) を使っている場合は、移動する場合に適しては Skype アプリを使ってます。国内/国際通話に使用安価はできます。電話会議を押したまま、ビデオ通話、およびプレゼンテーション用にデスクトップを共有するもことができます。[単価と [お支払い方法を確認](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)してください。
    
- **オプション 2 です。、プランをアップグレードして、電話システムと通話プランを購入する Office 365 の**します。およびを見つけるどの程度このコストとし、切り替える、[ビジネス製品 - 管理者向けヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)には、それらを行うにはすべてのアイテムがある最も簡単な方法です。
    
詳細については、[計画一般法人向け Office 365 の設定](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)を参照してください。
  
## <a name="2-sign-in-to-office-365"></a>2. へのサインインに Office 365
<a name="bkmk_signin"> </a>

Skype for Business Online は、Office 365 サービスのスイートの一部です。Skype for Business Online をセットアップするには、Office 365 にサインインする必要があります。その方法を示します。
  
1. Office 365 ユーザー ID (たとえば、 *rob@fourthcoffee.com* ) を探します。Skype for Business Online の購入時に作成した Office 365 ユーザー ID を含む Microsoft Online Services チームからメールを受信します。メールでは、次のようなものが表示されます。
    
    ![For Business Online Skype にサインアップした後に受信した、ようこそメールの例。Office 365 ユーザー id が含まれています。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. Office 365 管理センターにサインインし、Office 365 ユーザー ID とパスワードを入力します。サインインした後、Office 365 管理センターが表示されます。
    
    ![どのような Office 365 管理センターの例は次のように、ある場合は、Skype for Business Online を計画します。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## <a name="3-set-up-your-domain-and-users"></a>3. ドメインとユーザーを設定します。
<a name="bkmk_users"> </a>

これで、Office 365 にサインインしている、Skype for Business Online を使用、組織のドメインとユーザーを設定できます。
  
1. [ドメインを追加して Office 365 にユーザー](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Office 365 のセットアップ ウィザードを使用して、Office 365 でカスタム ドメイン (例*: fourthcoffee.com*) を設定します。**既定では、Office 365 のセットアップ ウィザードには、for Business Online の Skype の設定と Skype for Business ユーザー Id の作成が含まれています**。既に Office 365 用にドメインをセットアップするウィザードを使用した場合は、この手順を完了しました。
    
2. [ドメインと DNS の接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): ドメインと DNS の設定が正しいことを確認する - ドメインのトラブルシューティング -、ツールを使用します。これでこれを行うため、今後問題のソースとして DNS の設定を削除することができます後でセットアップの問題が発生を把握するために大きく役立ちますが移動されます。
    
3. [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): ほとんどの小規模企業は、この手順を実行する必要はありません。**Web パーツへのアクセスを制限しているファイアウォールまたはプロキシ サーバーがある場合**は、Skype for Business Online エンドポイント アクセスを許可するルールを作成する必要があります。これは、ファイアウォール、プロキシ サーバーの設定が発生したユーザーによって実行される最適な高度な手順です。いない場合このする前に、する Skype for Business をセットアップする[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。
    
## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. IM と、組織内でプレゼンスを設定します。
<a name="bkmk_IM"> </a>

インスタント メッセージング (IM) とプレゼンス ([Skype for Business で自分のプレゼンス情報へのアクセス制御](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) は、Skype for Business に付属する基本的な機能です。既定では、ビジネスに相互 Skype と IM を使用できます。
  
1. **他の Skype for Business ユーザーと通信できるユーザーを選択します。**
    
  - [ユーザーが外部の Skype for Business ユーザーに連絡できるようにします。](allow-users-to-contact-external-skype-for-business-users.md)両方する*と*その他のビジネスは、システムを構成する必要があります。
    
    **重要**: rob@contosowest.com ina@contosoeast.com] など、ビジネスで 2 つのドメインを持っている場合は、他のすべてのユーザー通信できるように、この手順を実行する必要があります。
    
  - 組織外の[、Skype for Business ユーザーが Skype の連絡先を追加します。](let-skype-for-business-users-add-skype-contacts.md)
    
2. **同僚がオンラインかどうかを表示できるユーザーの選択:**オンライン状態し、は何かの空き時間情報、使用可能な取り込み中、退席中、またはプレゼンテーションなど、プレゼンス機能を示しています。
    
    ![個人的なメッセージをその人のオンライン状態の例です。](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    ビジネスでは、すべてのユーザーの既定の設定を選択できます。
    
  - 組織内のすべてのユーザーにその人のオンライン プレゼンスを自動的に表示します。
    
  - その連絡先にのみその人のオンライン プレゼンスを表示します。
    
手順については、 [Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)を参照してください。
  
## <a name="5-download-and-install-skype-for-business"></a>5. ダウンロードして、Skype for Business をインストールします。
<a name="bkmk_download"> </a>

使用するには Skype for Business PC、Mac、またはモバイル デバイスのして、ビジネスで他のユーザーが最初のデバイスで Skype for Business のダウンロードをインストールする必要があります。
  
- [Skype for Business をインストールする](http://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): は Office 365 ポータルからアプリをダウンロードして、その、PC または mac インストールする方法の手順
    
- [Skype for Business クライアントを Office 365 の展開](deploy-the-skype-for-business-client-in-office-365.md): 大企業のアプリを展開するための手順です。
    
- [Skype for Business をインストールする](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): ダウンロード、インストール、および Android デバイス、iOS デバイスでは、Windows phone で Skype for Business にサインインします。
    
- [携帯電話の通知を無効または有効にする](turn-on-or-off-mobile-phone-notifications.md): ビジネスでの他のユーザーとは、受信、および不在着信したインスタント メッセージに関する通知を受信できます Skype for Business のモバイル デバイスにインストールされているが、します。
    
## <a name="6-test-to-make-sure-everything-is-working"></a>6. 動作しているかどうかを確認するテストします。
<a name="bkmk_test"> </a>

最初に、ビジネスでの他のユーザーとできるかどうかをテスト[ビデオ: 向けのサインインと Skype サインアウト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)します。それぞれのプレゼンスを表示すると、クイック会議を実行するくださいとその他] に IM ができることを確認してください。
  
問題が起きる場合次の操作を行います。
  
- [Skype for Business へのサインインのヘルプが必要ですか?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)一般的なサインインの問題です。
    
- [ビジネス製品 - 管理者向けヘルプのサポートに問い合わせてください](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。ここでは解消ためです。
    
## <a name="do-you-want-to-set-up-other-available-features"></a>使用可能なその他の機能を設定しますか。
<a name="bkmk_more"> </a>

その他の機能をセットアップする前にライセンスがあることを確認します。[Skype Business および Microsoft チーム アドオン ライセンスを許可します。](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
### <a name="set-up-audio-conferencing"></a>音声会議をセットアップします。

組織のユーザーは、電話を使用して、会議にコールインする必要があります。Skype for Business には、これだけの電話会議の機能が含まれています。ユーザーに Skype for Business 会議の Skype を使用して for Business アプリをモバイル デバイスや PC ではなく、電話を使用して呼び出すことができます。
  
ステップ バイ ステップのセットアップ手順については、Office 365 での[Skype for Business とチームの Microsoft の音声会議をセットアップする](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)を参照してください。
  
### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>電話システムと Office 365 での通話プランを設定します。

Office 365 で電話システムで機能を使用すると、ビジネス用電話システムします。組織内のビジネス ユーザーの他の skype 通話は、無料と発信者の内外から他の従業員がボイス メールを受け取ることができます。ここでは、電話システムで表示します。
  
プランの呼び出しサービスを追加すると、向け Skype で主要な電話番号が表示従業員。でき、ビジネスの外部で電話をかけたり受けたりすることができます。VoIP 電話、コンピューター、モバイル デバイス間での音声通話に設定できます。また、事態した場合に備えてについて 911 を呼び出すことができます。
  
ステップ バイ ステップのセットアップ手順については、設定を参照してください。 プランの呼び出しをセットアップします。
  
### <a name="set-up-skype-meeting-broadcast"></a>Skype 会議メディアを設定します。

Skype 会議メディアとは、ホストを作成して、最大 10,000 人の参加者との会議をブロードキャストする機能です。**、実際の操作の詳細については、次を参照してください[Skype 会議メディアとは何ですか?](http://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) ** 。
  
Skype 会議メディアを設定する手順の概要を示します。
  
1. [割り当てまたは一般法人向け Office 365 のライセンスを削除する](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): すべてのユーザーは**ホスト**にブロードキャスト会議に**Skype for Business Online**または**Enterprise のプラン**のライセンスを割り当てます。
    
2. [Skype 会議メディアを有効にする](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): 既定では、この機能が有効になっています。有効にした後ことは、ユーザーは、組織内の他のユーザーとの会議をブロードキャストのホストにできるようになります。
    
3. [Skype 会議メディア用にネットワークを設定する](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): 場合は、ホスト ウェビナーをブロードキャストの他の参加者と組織外部のネットワークを構成するのにはする必要があります。
    
4. [スケジュールする Skype 会議メディア](http://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)[に参加する Skype 会議メディア](http://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe)を持っている: *https://portal.broadcast.skype.com*で Skype 会議メディアをスケジュールし、他のユーザーが作業をブロードキャスト会議に参加しようとするかどうかを確認します。会議します。
    
## <a name="learn-about-network-connectivity-requirements"></a>ネットワーク接続の要件の詳細についてください。
<a name="bkmk_more"> </a>

音声、ビデオ、およびアプリケーション共有 Skype for Business での品質は大幅に影響を受ける-エンドツー エンド ネットワーク接続の質します。操作が最適なことが重要、会社のネットワークと Skype for Business Online の間の高品質の接続があるかどうかを確認します。ネットワークとチューニングについては、 [Skype for Business Online のパフォーマンスに微調整する](http://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)を参照してください。
  
## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>すべて実行セットアップよいですか。Skype for Business 使いを開始します。
<a name="bkmk_more"> </a>

[Skype for Business のトレーニング](http://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): をすぐに使い始めるためのトレーニング トピックのリストを確認します。
  
[Skype for Business 電話会議を開始します。](http://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[Skype for Business でビデオ デバイス オプションを設定します。](http://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[Skype for Business 使い、ビデオ通話を送受信します。](http://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>関連トピック
<a name="bkmk_more"> </a>

[Skype for Business Server と Skype for Business Online の間のハイブリッド接続を計画します。](https://go.microsoft.com/fwlink/p/?linkid=400791)
  

