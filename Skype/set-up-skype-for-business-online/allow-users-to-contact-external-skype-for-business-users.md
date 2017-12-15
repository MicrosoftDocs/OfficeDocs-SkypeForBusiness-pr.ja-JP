---
title: "ユーザーが外部の Skype for Business ユーザーに連絡できるようにする"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# ユーザーが外部の Skype for Business ユーザーに連絡できるようにする

> [!NOTE]
> Skype for Business のフェデレーションは、21Vianet が運用している Office 365、および Office 365 のドイツの組織では利用できません。 
  
次の場合にこの記事の手順を実行します。
  
- 会社内の異なるドメインにユーザーが存在する場合。たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com が存在する場合です。
    
- 組織内のユーザーが、組織外の特定の企業にいる人と連絡するために Skype for Business を使用するようにする場合。
    
- または、世界中で Skype for Business を使用する他のすべてのユーザーが、メール アドレスを使用して自分を検索して連絡できるようにしたい場合。Skype for Business の既定の設定を使用する場合、これは自動的に機能します。機能しない場合は、自分のドメインが他のユーザー側でブロックされていないことを確認する必要があります。
    
## ユーザーが行う企業間の通信を有効にする
<a name="bk_preview"> </a>

Office 365 でこれを行うには、[Office 365 の管理者ロールについて](about-office-365-admin-roles.md)が必要です。
  
1. Office 365 の管理者アカウントでサインインします。
    
2. Office 365 管理センター で、[ **管理センター**]、[ **Skype for Business**] の順に移動します。
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. [ **Skype for Business 管理センター**] で、[ **組織**]、[ **外部通信**] の順に選びます。
    
4. 特定の会社または別のドメインのユーザーとの通信を設定するには、ドロップ ダウン ボックスで [ **許可したドメインに対してのみオンにする**] を選びます。
    
    または、世界中で Skype for Business ポリシーがある他のすべてのユーザーとの通信を有効にする場合は、[ **禁止したドメインを除いてオンにする**] を選びます。これは既定の設定です。
    
5. [ **禁止したドメインまたは許可したドメイン**] で、[ **+**] を選んで許可するドメインの名前を追加します。
    
6. 他の組織でも、管理者が [ **Skype for Business 管理センター**] で同じ手順を行うことを確認します。たとえば、他の組織の管理者は、こちらの会社のドメインを [ **許可されているドメイン**] リストに入力する必要があります。
    
7. Windows Firewall を使用している場合は、Skype for Business が必要なポートを自動的に開きます。
    
    組織でネットワーク上のコンピューターがインターネットに接続するのを制限するために別のファイアウォール ソリューションを使用している場合は、お使いのクライアント コンピューターが下記の [Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) にアクセスできることを確認してください。これにより、ファイアウォールまたはプロキシのインフラストラクチャ構成の発信許可リストに、これらの FQDN を追加する必要がある場合があります。 ***.api.skype.com、*.users.storage.live.com、graph.skype.com** 。これらのポートをお使いのファイアウォールで開く方法については、ファイアウォールに付属しているマニュアルで確認してください。
    
    開く必要があるすべてのポートの一覧については、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo)」の記事の「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)」をご覧ください。
    
8. **テストのために最大 24 時間待機します** 。外部通信設定を変更したときはいつでも、変更がデータ センター全体に行き渡るまでに最大 24 時間かかる場合があります。
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 自分のユーザーに対して、無料のコンシューマー アプリである Skype を使用しているすべてのユーザーを検索したり、それらのユーザーと IM で連絡したりできるようにすることができます。詳しくは「[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)」をご覧ください。
  
## テストとトラブルシューティング
<a name="bk_preview"> </a>

 **ユーザーが企業間の通信をセットアップするときに生じる最も一般的な問題は、[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)正しい状態にすることです。**
  
セットアップをテストするには、会社のファイアウォールの背後に位置しない Skype for Business の連絡先が必要です。
  
1. 外部通信設定を変更した後、 **テストのために最大 24 時間待機** します。
    
2. Skype for Business で、Skype for Business 連絡先を検索し、チャットのリクエストを送信します。
    
    会社のポリシーのために送信できなかったというメッセージを受信する場合は、お使いの[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)をダブルチェックする必要があります。
    
3. Skype for Business 連絡先に対して、チャットのリクエストを送信してくれるよう頼みます。連絡先からリクエストを受け取れない場合は、お使いのファイアウォール設定に問題があります (連絡先側でファイアウォール設定に問題がないことを確認済みであることを前提としています)。
    
4. 問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、コーヒー ショップなどの、お使いのファイアウォールの背後に位置しない Wifi の場所に移動して、Skype for Business を使用して連絡先にチャットするリクエストを送信します。メッセージがここを経由すれば送られるのに職場では送られない場合は、ファイアウォールが問題であることが分かります。
    
## 別の会社との接続時に、他のユーザーを見つけたり、自分を見つけらるようにする方法
<a name="bk_preview"> </a>

他の Skype for Business ユーザーとの外部通信を有効にすると、ユーザーは Rob@contoso.com などのサインイン名を検索することによってフェデレーションされた Skype for Business ユーザーを見つけられるようになります。見つけたユーザーを連絡先のリストに追加する必要があります。
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## フェデレーション企業との通信の設定に関するヒント
<a name="bk_preview"> </a>

- Skype for Business 2015 と Skype for Business Online との間のフェデレーションを構成するには、TechNet の記事「[Skype for Business Online とのフェデレーションを構成する](https://technet.microsoft.com/en-us/library/jj205126.aspx)」をご覧ください。
    
- Lync と Skype for Business Online との間のフェデレーションを構成するには、TechNet の記事「[Lync Online の顧客のためのフェデレーション サポートの構成](https://technet.microsoft.com/en-us/library/hh202193.aspx)」をご覧ください。
    
- Office 365 の 2 名の Skype for Business ユーザーがお互いに個別のドメインで通信しているときは、両方の組織で有効な Skype for Business 機能 (ビデオ会話やデスクトップ共有) のみを使用できます。
    
- 組織内の Skype for Business ユーザーがインプレース保持または訴訟ホールドになると、そのユーザーとその他の Skype for Business または Skype ユーザーとの間の IM での会話は、メールボックスの [ **回復可能なアイテム**] に保存されます。これらの会話は、メールボックスの [ **会話履歴**] フォルダーには保存されません。
    
## 特定の個人について外部の通信をオフにする
<a name="bk_preview"> </a>

外部の通信を会社全体について有効にした後で、特定の個人についてオフにすることができます。
  
1. Office 365 の管理者アカウントでサインインします。
    
2. Office 365 管理センター で、[ **ユーザー**]、[ **アクティブなユーザー**] の順に移動します。
    
3. ユーザーの一覧でユーザーを選択し、[ **その他の設定**] で [ **Skype for Business のプロパティを編集する**] をクリックします。
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. [ **Skype for Business 管理センター**] で、[ **外部の通信**] を選びます。
    
    [ **オプション**] ページで、すべての選択がオンになります。無効にする通信の選択をオフにします。次の画像は、Jakob が信頼している他の企業のユーザーと通信できるようになり、その他の Skype ユーザーとは通信できない状況を示します。
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. [ **保存**] を選びます。
    
> [!NOTE]
> 変更が有効になるまで最大 24 時間かかる場合があります。 
  
## 
<a name="bk_preview"> </a>

 *この記事の最終更新日: 2017 年 3 月 23 日* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## 関連トピック
<a name="bk_preview"> </a>

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)
  
[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
  

