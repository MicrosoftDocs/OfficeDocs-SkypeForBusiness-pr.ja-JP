---
title: "Skype for Business Online インストールをテストする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 19873b1f-8f7e-4dd8-92f4-2ce11344ed5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn to save time, support calls and increase satisfaction by setting up test accounts and computers, and testing dial-in conferencing, online features such as person-to-person calls, conferencing, and sign in and out. '
ms.openlocfilehash: 94a167dad9ab745993315450717e7efc7c5e00bc
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="test-your-skype-for-business-online-installation"></a>Skype for Business Online インストールをテストする

[] インストールした Skype for Business Online を、組織のすべてのユーザー用にセットアップする前にテストすることで、時間を節約し、サポートへの電話を減らして、ユーザーの満足度を向上させることができます。
  
必要なものは以下のとおりです。
  
- 少なくとも 3 つの Office 365 アカウント (自分のアカウントと、その他に少なくとも 2 つ)。
    
- テスト アカウントごとに 1 台のコンピューター。組織内の通常のコンピューターと同様にセットアップします。
    
- Skype for Business Online の電話会議プロバイダーがセットアップされたアカウント。詳細については、「[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)」をご覧ください。
    
## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください。

> [テスト アカウントをセットアップする](test-your-skype-for-business-online-installation.md#__toc328126910)
    
> [テスト コンピューターをセットアップする](test-your-skype-for-business-online-installation.md#__toc328126911)
    
> [電話会議をセットアップする](test-your-skype-for-business-online-installation.md#__toc328126912)
    
> [Skype for Business Online の機能とデバイスをテストする](test-your-skype-for-business-online-installation.md#__toc328126913)
    
## <a name="set-up-test-accounts"></a>テスト アカウントをセットアップする
<a name="__toc328126910"> </a>

1. Go to **Admin** > **Office 365** > **Users and groups**, then select add![Add](../images/328ffb57-5f31-430a-b653-4a6b8e76d338.png) and enter the required information.
    
2. 手順 4 (メール) まで進んだら、自分のメール アドレスを入力します。次に、新しいユーザーの名前とパスワードを記録します。 
    
3. 手順 1 と手順 2 を繰り返して、必要な数だけテスト アカウントをセットアップします。Skype for Business Online のオンライン会議機能をテストするには、少なくとも 2 つのアカウント (自分自身のアカウント以外に) が必要です。 
    
## <a name="set-up-test-computers"></a>テスト コンピューターをセットアップする
<a name="__toc328126911"> </a>

各テスト コンピューター上で、次の手順を実行します。
  
1. Office 365 のホーム ページに移動し、テスト アカウントのいずれかの資格情報でサインインします。
    
2. [ **設定**] ![設定: プロファイルを更新し、ソフトウェアをインストールして、クラウドに接続する](../images/4b83e9cb-c7e4-46c8-b3d1-cfee017123ae.png) に移動し、[ **ソフトウェアをインストールしてクラウドに接続する**] をクリックします。 
    
## <a name="set-up-audio-conferencing"></a>電話会議をセットアップする
<a name="__toc328126912"> </a>

Skype for Business Online 会議に電話でアクセスできるようにするには、アカウントに電話会議プロバイダーをセットアップします。次の情報を受け取ります。
  
- 有料ダイヤルイン電話番号と、利用できる場合はフリーダイヤルの番号。
    
- 組織で会議をスケジュールまたは進行するユーザーごとの会議コードと個人識別番号 (PIN)
    
ユーザーを電話会議向けにセットアップすると、そのユーザーはダイヤルイン番号と会議コードが記載された自動送信のメール メッセージを受け取ります。また、この情報は、新しい Skype for Business の会議出席依頼にも自動的に追加されます。
  
詳細については、「[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)」をご覧ください。 
  
 **テスト ユーザーのアカウントに電話会議情報を追加するには**
  
1. Click **Audio Conferencing** > **Uusers**.
    
2. ダイヤルイン会議向けにセットアップするユーザーの名前をクリックして、[ **編集**] ![編集](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)をクリックします。
    
3. 電話会議プロバイダーを選択して要求された情報を入力し、[ **保存**] をクリックします。
    
|**電話会議の設定**|**説明**|
|:-----|:-----|
|**プロバイダー** <br/> |一覧から電話会議プロバイダーを選びます。  <br/> |
|**有料電話番号** (必須) <br/> |電話会議プロバイダーから入手した電話番号です。Skype for Business の会議出席依頼に表示される番号の書式を設定します。  <br/> |
|**フリー ダイヤル番号** <br/> |電話会議プロバイダーから入手した電話番号です。Skype for Business の会議出席依頼に表示される番号の書式を設定します。  <br/> |
|**パスコード** <br/> |このユーザーのパスコード (会議コード) です。  <br/> |
   
## <a name="test-skype-for-business-online-features-and-devices"></a>Skype for Business Online の機能とデバイスをテストする
<a name="__toc328126913"> </a>

主要な Skype for Business Online 機能が正常に動作していることを確認します。
  
 **サインインとサインアウト**
  
|**タスク**|**期待される結果**|
|:-----|:-----|
|[Lync Online へのサインインとサインアウト](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |サインインすると、Skype for Business メイン ウィンドウが開き、指定したプレゼンス状態が表示されます。  <br/> |
|[Lync Online へのサインインとサインアウト](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Skype for Business サインイン画面が表示されます。  <br/> |
|[Lync Online へのサインインとサインアウト](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Skype for Business ウィンドウが閉じ、Windows 通知領域に Skype for Business が表示されなくなります。  <br/> |
   
サインインできない場合は、「[Skype for Business Online で発生するサインイン問題をトラブルシューティングする方法](https://support.microsoft.com/kb/2541980)」をご覧ください。
  
 **連絡先、プレゼンス、インスタント メッセージング**
  
|**タスク**|**期待される結果**|
|:-----|:-----|
|[Skype for Business で IM を送信する](http://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Skype for Business 会話ウィンドウが開きます。何かを入力すると、会話相手から返信されます。  <br/> |
|[Skype for Business で IM を送信する](http://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Skype for Business 会話ウィンドウが開きます。何かを入力すると、会話に参加している全員から返信されます。  <br/> |
|[連絡先を名または姓で検索する](https://support.office.live.com/article/29fa2061-f679-4e0d-902d-736b67774c8b#BKMK_ContactsFAQ) <br/> |入力するとすぐに検索結果が表示され始めます。  <br/> |
|[Lync for Office 365 についてのよく寄せられる質問 (FAQ)](http://support.office.com/article/29fa2061-f679-4e0d-902d-736b67774c8b.aspx#BKMK_ContactsFAQ) <br/> |選択した連絡先グループに、追加した連絡先が表示されます。  <br/> |
|[Skype for Business (Lync) でプレゼンス状態を変更する](http://support.office.com/article/ef8998cc-7801-4b62-81ba-9a2c1630f9e5) <br/> |新しいプレゼンス状態が他のユーザーの連絡先リストに反映されます。  <br/> |
|[連絡先カードの使用](http://support.office.com/article/19870880-FC90-46B0-9C60-C398518E9FBC) <br/> |個人の連絡先カードが、個人の名前の近くに表示されます。  <br/> |
   
 **ユーザー間の通話**
  
|**タスク**|**期待される結果**|
|:-----|:-----|
|[Lync 音声通話の発信と受信](http://support.office.com/article/39342f16-4d16-44de-a806-0b2b566f3886) <br/> |会話ウィンドウが開き、発信音が鳴ります。発信相手がデスクトップ通知を受け取り、通話を承諾すると、通話が接続され、会話ウィンドウが更新されます。  <br/> |
|[Skype for Business (Lync) インスタント メッセージの会話に音声を追加する](http://support.office.com/article/21a098b2-63f1-4205-a9aa-532b6a67ea92) <br/> |通話が接続されると、相手に IM を送信したり、話したりすることができます。  <br/> |
|[Lync でデスクトップまたはプログラムを共有する](http://support.office.com/article/33aaa965-eb32-42a9-8a9b-cdfffa364842) <br/> |共有しているデスクトップまたはプログラムは、相手にも表示されます。  <br/> |
   
 **会議**
  
|**タスク**|**期待される結果**|
|:-----|:-----|
|[Lync 会議をセットアップする](http://support.office.com/article/258f9d20-f06c-49a4-a77f-7f5ac635bb5d) <br/> |指定した相手に会議出席依頼が送信されます。  <br/> |
|[Skype for Business (Lync) 会議の参加者設定を変更する](http://support.office.com/article/cee2aa78-d878-4a63-ad33-9c249fceced9) <br/> |オプションによって異なります。  <br/> **ヒント:** [ **アクセスと発表者**] で、[ **ロビーをバイパスするユーザー**] オプションのさまざまな設定を試すことができます。 <br/> |
|[Skype for Business (Lync) 会議に参加する](http://support.office.com/article/538716dc-f4f2-48c2-af96-587c62387b87) <br/> |接続すると、会話ウィンドウが開き、会議参加者リストに自分の名前が表示されます。  <br/> |
|[Skype for Business 会議または通話でマイクをミュートまたはミュート解除する](http://support.office.com/article/47399948-db7f-4ee5-8e61-53a94bb97704) <br/> |会議参加者リストの全員の名前の横に [ミュート] が表示されます。自分が話す音声のみが聞こえるようになります。  <br/> |
|[Skype for Business (Lync) 会議で PowerPoint のスライドをプレゼンテーションする](http://support.office.com/article/3910a2b2-01df-4b97-9451-322b598ede7e) <br/> |PowerPoint プレゼンテーションは、全員のコンピューターの Skype for Business 会議ステージ ウィンドウに表示されます。  <br/> |
|[Skype for Business (Lync) 会議でファイルを転送する](http://support.office.com/article/f6942910-bc1d-4a48-bf18-385778f08088) <br/> |アップロードすると、他の会議参加者が添付ファイルを表示し、ダウンロードできるようになります。  <br/> |
   
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
