---
title: "通話プランのセットアップ"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/15/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 57893158-1acd-44ac-acaf-19f58264a9e0

description: "Learn how in Office 365 Calling Plan (PSTN Calling plan) to buy and set up licenses, get phone numbers, add and assign emergency locations and phone numbers to users, and tell your users about their new phone numbers. "
---

# 通話プランのセットアップ

他の Skype for Business ユーザーへの通話は無料ですが、自分のユーザーが会社の外の電話番号に発信できるようにするには、Office 365 の国内通話プランまたは国際通話プランを取得します。これは、所属する組織で簡単にセットアップできます。
  
## 手順 1: ライセンスを購入して割り当てる

1. Office 365 の電話システム機能がプランに含まれていない場合は、[ **電話システム**] アドオン ライセンスを購入する必要があります。[ **電話システム**] ライセンスを取得した後、[[Office 365 向けの通話プラン](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md)] を購入します。「[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照して、ライセンスとプランを購入してください。
    
    > [!TIP]
    > **電話システム**のライセンスと、Office 365 の通話プランは組み合わせられているため、通話プランを購入するオプションを表示するには、先に **電話システム**のライセンスを持っている必要があります。 
  
2. 組織内のユーザーに最初にライセンスを割り当ててから、通話プランを割り当てます。「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。
    
## 手順 2: 電話番号を取得する

米国外に居住している場合は、セットアップの手順が多少異なります。これは、一部の国/地域の緊急対応の住所は、Office 365 から取得する電話番号または転送される電話番号とともに取得されるためです。したがって、米国外に居住している場合は、まず「[手順 3: 組織用の緊急対応の住所と場所を追加する](set-up-calling-plans.md#bkmk_add_addresses)」を実行してから「 **手順 2:電話番号を取得する** 」を実行します。
  
1. Office 365 からの電話番号を使用している場合は、次の手順に従います。 **別のサービス プロバイダーから既存の電話番号を転送する必要がある場合は、「[Office 365 への電話番号に転送します。](transfer-phone-numbers-to-office-365.md)」の手順に従います。**
    
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
3. **Office 365 管理センター**、[ **管理センター**]、[ **Skype for Business**]、[ **音声**] の順に移動します。
    
||
|:-----|
|**重要**: Skype for Business 管理センターの左のナビゲーションに [ **音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、 **電話システム**アドオン ライセンス、または **電話会議**アドオン ライセンスを少なくとも 1 件購入する必要があります。 |
   
4. [ **電話番号**] を選びます。保有する **電話システム**のライセンスの数が表示されるので、要求する電話番号の数を特定する際の参考になります。
    
    > [!TIP]
    > ライセンスを保有する電話番号より多くの電話番号を取得できます。取得できる電話番号の数を特定するには、ライセンスの 10% を加算してから 10 を加算します。たとえば、100 ライセンスを購入している場合は、120 の電話番号を取得できます。 
  
     ![The dashboard shows how many Cloud PBX licenses you have.](../images/6af8653d-4b9c-41fa-85b4-88e763d08f4c.png)
  
5. [ **新しい番号の追加**]、[ **新しいユーザー番号**] の順に選んで、[ **新しいユーザー番号を追加**] ページで、国/地域および市区町村選んで、番号を選択する国/地域および都市を選びます。
    
6. この地域で組織に必要な電話番号の数を [ **数量**] に入力し、[ **追加**] をクリックして予約を作成します。
    
    > [!CAUTION]
    > 電話番号を選ぶ時間は 10 分間あります。10 分後に、電話番号が Office 365 の電話番号のプールに返されます。 
  
    次の図では、2 つの異なる都市に対して電話番号が追加されており、取得するまでの残り時間が 9 分あることがわかります。
    
     ![At the Add user numbers page, specify the area where you want to get the numbers for.](../images/f6dc1ef3-0bf2-4b4f-b32c-ca27e69c5553.png)
  
7. [ **番号の表示**] を選択すると、電話番号の完全なリストが表示されます。これは、特定の電話番号を希望しない場合に役立ちます。
    
8. 目的の電話番号を選んでから [ **番号を取得**] を選択します。
    
9. [ **音声**] ページに戻り、取得したすべての番号が表示されます。
    
    ![At the Voice dashboard, you'll see all the phone numbers you acquired.](../images/4a9c681c-13f9-4cdc-a25b-93eb00d06b6c.png)
  
## 手順 3: 組織用の緊急対応の住所と場所を追加する
<a name="bkmk_add_addresses"> </a>

1. [ **音声**] ページで、[ **緊急対応の場所**]、[ **新しいアドレスを追加**] の順に選びます。
    
2. [ **新しい住所**] ウィンドウで、住所の名前を入力し、残りのボックスの入力を完了します。
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > 上の図のように、英語圏のお客様で街路名が数字の場合は、必ず末尾に「st」または「th」を付けます。 
  
3. [ **検証**] を選択します。
    
    必要な場合は、住所の訂正を求められます。
    
    > [!CAUTION]
    > 住所または公的アドレスの検証では、住所が正規の住所で、形式が正しいことが確認されます。緊急対応の住所の一部が誤っていても (市区町村名の誤入力など)、検証をパスすることがあります。誤記があっても検証をパスした場合、誤記がある市区町村名と住所の他の正しい部分の組み合わせによって、適切な緊急派遣センターに通話をルーティングするために十分な情報になります。 
  
    > [!TIP]
    > 緊急応答用に住所に修正が必要な場合は、住所が更新されたことを通知する緑色のバナーが表示されます。 
  
4. 住所が検証されたら、[ **保存**] を選びます。
    
## 手順 4: ユーザーに電話番号と緊急対応の住所を割り当てる
<a name="bkmk_add_addresses"> </a>

> [!TIP]
> この手順を実行する直前にさらにユーザーを追加すると、[ **音声ユーザー**] ページにユーザーが表示されるまでに **数時間** かかることがあります。これには遅延時間があります。
  
1. [ **音声ユーザー**] ページで、電話番号と緊急対応の住所を割り当てるユーザーを選択します。
    
2. 操作ウィンドウで [ **番号を割り当てる**] をクリックします。
    
3. [ **番号を割り当てる**] ページの [ **割り当てる番号を選択**] 一覧で、ユーザー用の電話番号を選びます。
    
4. 緊急対応の住所を選ぶには、ボックスに市区町村の名前を入力し、[ **検索**] を選びます。
    
    > [!IMPORTANT]
    > 米国外に居住している場合は、電話番号にすでに緊急対応の住所が指定されていますが、ここで変更できます。「[ユーザーの緊急対応の住所を割り当てるまたは変更する](assign-or-change-an-emergency-address-for-a-user.md)」をご覧ください。 
  
5. 電話番号と緊急対応の住所の両方を割り当てたら、[ **保存**] を選びます。
    
## 手順 5: 新しい電話番号をユーザーに通知する
<a name="bkmk_add_addresses"> </a>

新しい電話番号をユーザーに通知する場合は、メールを送信するか、または各組織が指定する方法で行うことをお勧めします。次に、ユーザーの Skype for Business アプリに電話番号がどのように表示されるかを示します。
  
1. デスクトップで Skype for Business にサインインします。
    
2. [ **設定**]、[ **ツール**]、[ **オプション**] の順に選びます。
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 次に、[ **電話**] を選びます。
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
  
## その他の情報
<a name="bkmk_add_addresses"> </a>

- 緊急対応の住所は、行政上の住所、所在地住所、または現住所と呼ばれることがあります。緊急対応の住所は、組織の事業所の場所を示す所在地住所または行政上の住所のことです。
    
- 緊急対応の場所は検証されません。緊急対応の住所だけが検証されます。
    
- 緊急対応の住所の詳細については、「[緊急対応の場所、アドレス、通話ルーティングの概要](what-are-emergency-locations-addresses-and-call-routing.md)」をご覧ください。
    
## 電話番号の割り当ての自動化
<a name="bkmk_add_addresses"> </a>

Windows PowerShell を使うことができる場合は、次のコマンドレットを使用して、ユーザーへの電話番号の割り当てを自動化できます。
  
- [Get-CsOnlineTelephoneNumber](https://technet.microsoft.com/en-us/library/mt243818.aspx): Business Voice Directory から電話番号を取得します。
    
- [Set-CsOnlineVoiceUser](https://technet.microsoft.com/en-us/library/mt243817.aspx): 電話番号を設定します。
    
詳しくは、「[クイック リファレンス: Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://technet.microsoft.com/en-us/library/dn362776%28v=ocs.15%29.aspx)」ご覧ください。
  
||
|:-----|
|![LinkedIn ラーニングのショート アイコンです。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Office 365 を初めてお使いの場合は**         、LinkedIn ラーニングによって提供された **Office 365 管理者および IT プロフェッショナル**向けの無料のビデオコースをご覧ください。 |
   
## ご意見を寄せてください。
<a name="BKMK_comment"> </a>

この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
  
## 関連項目
<a name="BKMK_comment"> </a>

#### 

[Skype for Business Online: 緊急通話の免責事項ラベル](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
  
[音声会議無料ダイヤルアウト期間](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

