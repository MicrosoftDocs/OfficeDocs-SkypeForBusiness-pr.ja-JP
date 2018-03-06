---
title: "Skype for Business Online のセットアップ"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.prod: office-online-server
localization_priority: Priority
ms.collection:
- Adm_O365_CommTopIssues
- Adm_O365_Setup
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- Alchemy
- DianeF_Adm_Simplified
- DianeF_Setup_HappyPath
- LeftNav_Adm_O365
- LIL_Placement
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e

description: "Learn to set up your domain, users, IM and presense for your organization to install Skype for Business. Also See how to set up dial-in conferencing, Cloud PBX and PSTN calling, and Skype Meeting broadcast. "
---

# Skype for Business Online のセットアップ

作成協力者: [![Diane Faigel](../images/e4ec7084-196e-4e04-bccc-e241da509abf.png)
  
](https://go.microsoft.com/fwlink/?linkid=847124)
  
Skype for Business をセットアップするには、Office 365 グローバル管理者の権限を持つ必要があります。Web のアクセスを部分的に制限するファイアウォールまたはプロキシ サーバーを利用している場合は、[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089) に Skype for Business のセットアップを依頼することを検討してください。
  
## Skype のセットアップ

ご利用の Office 365 サブスクリプションで Skype をセットアップする場合に、サポートが必要になるかもしれません。[この記事](https://support.office.com/article/https://support.office.com/en-us/article/Set-up-Skype-for-Business-Online-40296968-e779-4259-980b-c2de1c044c6e.aspx#bkmk_more)に記載されている手順を実行すれば、セットアップを完了できます。
  
## 1. Skype for Business のプラン

 **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** または **Business Essentials** をお持ちの場合は、Skype for Business を使用して、サブスクリプションを使用している社内の他のユーザーにオンライン通話を発信することができます。たとえば、社内のユーザーが 10 人である場合、下記の手順 2 から 6 までを実行した後に[IM およびオンライン会議に Skype for Business を使い始める](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) を使用して[Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) で相互に連絡を取り合うことや、Skype for Businessオンライン会議を開催することができます。また、オンライン会議に[Outlook で Skype for Business 会議を設定する](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA)こともできます。
  
Skype for Business を使用して、所属する企業の **外部** のユーザーとの *通話*  の発着信を行う場合は、次の操作を実行します。
  
- **オプション 1。無料の [Skype アプリ](https://www.skype.com/)** を使用します。小規模事業の場合 (たとえば 1 人から 2 人の組織) には、Skype アプリを使うと業務を円滑に進められます。国内通話と国際通話で利用する場合は、より安価な手段となります。電話会議を取り次いだり、ビデオ通話を発信したり、プレゼンテーションのためにデスクトップを共有したりすることもできます。[料金とお支払いオプションを確認してください](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled)。
    
- **オプション 2: ご利用のプランをアップグレードして、Office 365 電話システムと Office 365 通話プランを購入します** 。各プランの料金を確認して利用を切り替えるための最も簡単な方法は、[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)してすべての操作を代行してもらうことです。
    
詳細については、「[一般法人向け Office 365 のセットアップを計画する](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)」をご覧ください。
  
## 2. Office 365 にサインインする
<a name="bkmk_signin"> </a>

Skype for Business Online は、Office 365 スイートのサービスの一部です。Skype for Business Online をセットアップするには、Office 365 にサインインする必要があります。その手順を紹介します。
  
1. Office 365 のユーザー ID を確認します (例:  *rob@fourthcoffee.com*  など)。Microsoft Online Services チームから、Office 365 の購入時に作成した Skype for Business Online のユーザー ID が記載されているメールが送信されています。メールは次のように表示されます。
    
    ![Skype for Business Online にサインアップした後に受信したウェルカム メールの例です。 これには、Office 365 ユーザー ID が含まれています。](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. [https://portal.office.com/](https://go.microsoft.com/fwlink/p/?linkid=402333) にアクセスして、Office 365 のユーザー ID とパスワードを入力します。サインインすると、Office 365 管理センターが表示されます。
    
    ![Skype for Business Online プランを持っている場合の Office 365 管理センターの外観の例です。](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## 3. ドメインとユーザーをセットアップする
<a name="bkmk_users"> </a>

Office 365 にサインインしたら、ドメインと組織内のユーザーが Skype for Business Online を使用するようにセットアップできます。
  
1. [Office 365 でドメインの所有者の確認方法](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Office 365 セットアップ ウィザードを使用して、 でカスタム ドメイン (Office 365fourthcoffee.com など) をセットアップします。 **既定では、Office 365 セットアップ ウィザードには Skype for Business Online のセットアップ、Skype for Business のユーザー ID の作成が含まれています。** 既にウィザードを使用して Office 365 のドメインをセットアップした場合は、この手順は完了しています。
    
2. [ドメインと DNS の接続を確認する](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0 .aspx): ドメイン トラブルシューターなどのツールを使用して、ドメインと DNS の設定が正しいことを確認します。これによって、将来何か問題が発生した場合でも DNS 設定は原因から排除できますので、後でセットアップの問題を調べる手間を省くことに繋がります。
    
3. [Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): ほとんどの小規模事業では、この手順どおりに行う必要はありません。 **ただし、Web へのアクセスを部分的に制限するファイアウォールまたはプロキシ サーバーがある場合は** 、Skype for Business Online のエンドポイントへのアクセスを許可するためのルールを作成する必要があります。これは高度な手順であるため、ファイアウォールやプロキシ サーバーの設定の経験がある人に行ってもらうことをお勧めします。このような作業を行ったことがない場合は、[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)と契約して、Skype for Business のセットアップを依頼することを検討してください。
    
## 4. 組織内の IM とプレゼンスをセットアップする
<a name="bkmk_IM"> </a>

インスタント メッセージ (IM) とプレゼンス情報 ([Skype for Business のプレゼンス情報へのアクセスを制御する](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c#bkmk_presence)) は、Skype for Business の基本的な機能です。既定では、組織内のユーザーは相互に Skype と IM でやり取りをすることができます。
  
1. **組織内のユーザー以外に Skype for Business ユーザーがやり取りできるユーザー** を次の中から選びます。
    
  - [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](allow-users-to-contact-external-skype-for-business-users.md) 組織内 *および*  別の組織の両方でシステムを構成する必要があります。
    
    **重要**: 会社に rob@contosowest.com と ina@contosoeast.com のような 2 つのドメインがある場合は、この手順を実行して、すべてのユーザーが相互に通信できるようにする必要があります。
    
  - 組織外の [Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
    
2. **同僚がオンライン状態かどうかを表示できるユーザーを選ぶ:** プレゼンス機能を使うと、オンライン状態のユーザーが表示され、連絡可能、取り込み中、外出中、プレゼンテーション中などの状態が示されます。
    
    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    組織内のすべてのユーザーに次のような既定の設定を選ぶことができます。
    
  - 個人のオンライン プレゼンス情報を組織内の全員に自動的に表示する
    
  - 個人のオンライン プレゼンス情報を連絡先にのみ表示する
    
手順については、「[Skype for Business Online でプレゼンスを設定する](configure-presence-in-skype-for-business-online.md)」をご覧ください。
  
## 5. Skype for Business をダウンロードしてインストールする
<a name="bkmk_download"> </a>

Skype for Business を PC、Mac またはモバイル デバイスで使用するには、組織内の自分または自分以外の人がまず、デバイスにダウンロードされた Skype for Business をインストールする必要があります。
  
- [Skype for Business をインストールする](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Office 365 ポータルからアプリをダウンロードして、PC または Mac にインストールする方法。
    
- [Office 365 で Skype for Business クライアントを展開する](deploy-the-skype-for-business-client-in-office-365.md) : 大企業でアプリを展開する方法。
    
- [Skype for Business をインストールする](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Skype for Business を Android デバイス、iOS デバイス、Windows Phone にダウンロードしてインストールし、サインインします。
    
- [携帯電話の通知を有効または無効にする](turn-on-or-off-mobile-phone-notifications.md) : モバイル デバイスに Skype for Business をインストールすると、組織内の自分と自分以外の人は、着信したインスタント メッセージと不在時のインスタント メッセージに関する通知を受信することができます。
    
## 6. すべての機能が動作していることを確認するためのテストを行う
<a name="bkmk_test"> </a>

最初に組織内の自分と自分以外の人が [Skype for Business へのサインインと Skype for Business からのサインアウト](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451)できることをテストします。相互に IM の送受信ができることを確認し、相互のプレゼンスを表示して、簡単な会議を始めてみます。
  
問題がある場合は、次の操作を行います。
  
- [Skype for Business のサインインのヘルプ](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)して、一般的なサインインの問題を確認する。
    
- [一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)。役立つ情報が提供されます。
    
## 他の機能をセットアップする場合
<a name="bkmk_more"> </a>

他の機能をセットアップする前に、それらの機能を使用するためのライセンスを取得していることを確認します。[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
### 電話会議をセットアップする

組織内のユーザーは電話による会議への参加が必要なことがあります。Skype for Business では、このような状況のための電話会議の機能が含まれています。参加者は、モバイル デバイスや PC で Skype for Business アプリを使用する代わりに、電話を使って Skype for Business 会議にコールインできます。
  
詳細なセットアップ手順については、Office 365 の「[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)」をご覧ください。
  
### Office 365 の電話システムと通話プランをセットアップする

Office 365 の電話システム機能は組織に電話システムを提供する機能です。組織内の他の Skype for Business ユーザーへの通話は無料で、従業員は他の従業員または外部の発信者からのボイスメールを受け取ることができます。詳細については「電話システムで利用できる機能」をご覧ください。
  
通話プラン サービスを追加すると、従業員は Skype for Business で主な電話番号を取得します。従業員は外部の人に電話をかけたり、外部の人から電話を受け取ったりすることができます。VoIP 電話、PC およびモバイル デバイスを使用して音声通話を行うことができます。また、緊急時に 911 に通報して対応を要請することもできます。
  
詳細な手順については、「通話プランをセットアップする」をご覧ください。
  
### Skype 会議ブロードキャスト をセットアップする

Skype 会議ブロードキャスト は、最大で 10,000 人の出席者を含む会議を作成、開催、およびブロードキャストする機能です。 **機能の詳細については、「[Skype 会議ブロードキャストとは](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)」をご覧ください。**
  
Skype 会議ブロードキャスト のセットアップ手順の概要を以下に示します。
  
1. [一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): ブロードキャスト会議を **開催する** すべてのユーザーに、 **Skype for Business Online** または **Enterprise プラン** のライセンスを割り当てます。
    
2. [Skype 会議ブロードキャストを有効にする](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md) : 既定では、この機能は無効になっています。有効にすると、ユーザーは組織内の他のユーザーとのブロードキャスト会議を開催することができます。
    
3. [Skype 会議ブロードキャスト用にネットワークをセットアップする](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md) : 組織外の出席者とのウェビナーおよび他のブロードキャストを開催するには、ネットワークを構成する必要があります。
    
4. [Skype 会議ブロードキャストをスケジュールする](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553)して、[Skype 会議ブロードキャストに参加する](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe):  *https://portal.broadcast.skype.com*  で Skype 会議ブロードキャスト を予約し、誰かに会議に参加してもらうことで、ブロードキャスト会議が正しく機能するかどうかを確認します。
    
## ネットワーク接続要件を確認する
<a name="bkmk_more"> </a>

Skype for Business のオーディオ、ビデオ、アプリケーション共有の品質は、エンドツーエンド ネットワーク接続の品質に大きく左右されます。最適な操作性を得るには、会社のネットワークと Skype for Business Online 間に高品質の接続を確立することが重要です。ネットワークとチューニングの情報については、「[Skype for Business Online のパフォーマンスの調整](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802)」をご覧ください。
  
## セットアップはすべて完了しましたか? Skype for Business の使用を開始する
<a name="bkmk_more"> </a>

[Skype for Business についてもっと知る](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): トレーニング トピックに関するこのリストを確認すると、すばやく開始するのに役に立ちます。
  
[Skype for Business 電話会議を開始する](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[Skype for Business のビデオ デバイス オプションを設定する](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[Skype for Business を使用してビデオ通話を発信および受信する](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
## 
<a name="bkmk_more"> </a>

||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## 関連トピック
<a name="bkmk_more"> </a>

[Skype for Business Server と Skype for Business Online 間のハイブリッド接続を計画する](https://go.microsoft.com/fwlink/p/?linkid=400791)
  

