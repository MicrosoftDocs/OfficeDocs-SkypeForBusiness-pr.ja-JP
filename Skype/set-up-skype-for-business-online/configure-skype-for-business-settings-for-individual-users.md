---
title: "管理者 個別のユーザーの Skype for Business の設定を構成する"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836

description: "Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. "
---

# 管理者: 個別のユーザーの Skype for Business の設定を構成する

この記事では、管理者が少数のユーザーのために Skype for Business を構成する方法について説明します。これらの手順を一括で実行するために、使用可能な Windows PowerShell コマンドレットへのリンクも記載してあります。
  
会社内のすべてのユーザーが外部のユーザーとの通信を許可 (または遮断) するには、次をご覧ください。
  
- [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](allow-users-to-contact-external-skype-for-business-users.md) : 組織で高度な Skype for Business 機能 (デスクトップの共有、オンライン状態のユーザーの検索) を使用することを許可して特定の信頼済み (フェデレーション) の会社のユーザーと通信できるようにします。また、特定のドメインとの通信を遮断する方法についても説明します。
    
- [Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md) : 組織で Skype for Business を使用することを許可して、無料アプリの Skype を使う IM ユーザーを検索できるようにします。
    
## 1 人のユーザーの全般設定を構成する
<a name="__toc325019204"> </a>

これらの手順を実行するには、[Office 365 の管理者ロールについて](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. [ **管理センター**]、[ **Skype for Business**] の順に選びます。
    
3. [ **ユーザー**] を選びます。
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. 編集するユーザーを選びます。
    
5. 右側のウィンドウで、[ **編集**] を選びます。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. [ **全般**] オプション ページで、変更する機能の横のチェック ボックスをオンまたはオフにして、[ **保存**] をクリックします。
    
|**オプション**|**詳細**|
|:-----|:-----|
|音声および HD ビデオ  <br/> |このユーザーが音声会議、音声とビデオによる会議を記録することを許可したり、会議のスケジュール設定を行えない状態 (なし) にします。  <br/> |
|会話および会議のレコーディング  <br/> |このユーザーが記録できる内容を選びます。  <br/> このオプションは、Skype for Business Basic では利用できません。  <br/> |
|コンプライアンスのため、アーカイブされていない機能はオフにする  <br/> | 電子的に保存した情報の保管を法律で要請されている場合は、このオプションを選びます。 <br/>  このオプションを選ぶと、Exchange 管理センターで設定された[インプレース保持](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx)が有効なときに取り込まれない機能がオフになります。これにより次の機能がオフになります。  <br/>  インスタント メッセージングを使用したファイルの転送 <br/>  OneNote の共有ページ <br/>  PowerPoint のコメント <br/> |
   
これらの設定を一括で構成するには、PowerShell を使います。[Skype for Business Online のポリシーを管理する](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx)」をご覧ください。
  
## 外部通信を遮断する
<a name="__toc325019206"> </a>

会社内のすべてのユーザーに対して[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)した後に、次の手順を実行して特定の個人について選択的に外部通信を遮断することができます。
  
1. [ **ユーザー**] を選び、設定を無効にするユーザーを選んで、[ **編集**]![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) を選びます。
    
2. [ **外部通信**] を選んで、必要に応じてオプションをオフにします。
    
  - **外部の Skype for Business ユーザー**: フェデレーションのドメイン内の Skype for Business ユーザーとの通信を可能にしない場合は、このボックスをオフにします。
    
  - **外部の Skype ユーザー**: 無料の Skype アプリを使用しているユーザーとの通信を可能にしない場合は、このボックスをオフにします。
    
3. [ **保存**] をクリックします。
    
これらの設定を一括で構成するには、PowerShell を使います。[Skype for Business Online での外部ユーザーおよび組織との通信を管理する](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx)」を参照してください。
  
## 1 人のユーザーの電話会議の設定を編集する
<a name="__toc314837483"> </a>

1. [ **ユーザー** ] を選び、電話会議の設定を編集する対象のユーザーを選択して、[ **編集**]![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) を選びます。
    
2. [ **電話会議**] を選び、電話会議プロバイダーを選択し、要求された情報を入力または変更して [ **保存**] をクリックします。
    
|**電話会議の設定**|**説明**|
|:-----|:-----|
|**プロバイダー名** <br/> |一覧からプロバイダーを選びます。  <br/> |
|**有料電話番号** (必須) <br/> |サードパーティの電話会議プロバイダーを利用している場合、これらの電話番号は電話会議プロバイダーから受け取った番号です。ユーザーが電話会議プロバイダーとして利用しているのが Microsoft である場合は、これらは電話会議ブリッジで設定されている番号になります。Skype for Business および Microsoft Teams の会議リクエストで、表示したい電話番号の書式を設定します。  <br/> |
|**フリー ダイヤル番号** <br/> |サードパーティの電話会議プロバイダーを利用している場合、これらの電話番号は電話会議プロバイダーから受け取った番号です。ユーザーが電話会議プロバイダーとして利用しているのが Microsoft である場合は、これらは電話会議ブリッジで設定されている番号になります。Skype for Business および Microsoft Teams の会議リクエストで、表示したい電話番号の書式を設定します。  <br/> |
|**電話会議 ID と PIN** (必須) <br/> |参加者の PIN、または電話会議番号です。そのユーザーによってスケジュール設定されている会議に参加するために使用され、サードパーティの電話会議プロバイダーから提供されます。. ユーザーが Microsoft を電話会議プロバイダーとして利用している場合は、これは必須ではありません。  <br/> |
   
これらの設定を一括で構成するには、PowerShell を使います。「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](../audio-conferencing-in-office-365/set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)」をご覧ください。
  
## 
<a name="__toc314837483"> </a>

||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## 関連トピック
<a name="__toc314837483"> </a>

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

