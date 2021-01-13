---
title: Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: '概要: Skype for Business Server と Skype for Business で 2 要素認証を使用します。'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806543"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する
 
**概要:** Skype for Business Server と Skype for Business で 2 要素認証を使用します。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>初めて Skype for Business にサインインする

サインイン情報は、通常、Skype for Business のインストール時に自動的に構成されます。 ただし、初めて Skype for Business を使用する場合は、クライアントを手動で開始する必要があります。
  
### <a name="to-sign-in-for-the-first-time"></a>初めてサインインするには

1. 組織のネットワークにログオンします。
    
2. [すべての **プログラム**  >  **を**  >  **起動する] Skype for Business を選択します**。
    
    サインイン画面が表示されます。
    
    - サインイン アドレス ボックスが既に入力されている場合は、表示されているアドレスが正しいか確認します。
    
    - 正しく表示されない場合、またはボックスが空の場合は、サインイン アドレスを入力します (通常、これはメール アドレスと同じです)。
    
    - 空のパスワード ボックスが表示される場合は、パスワードを追加します。
    
3. [ **サインイン] を選択します**。
    
## <a name="sign-out-of-skype-for-business"></a>Skype for Business からサインアウトする

Skype for Business の使用が完了したら、[ファイル] メニューから表示を閉じるか、セッションからサインアウトするか、プログラムを終了できます。 次の表に、オプションの違いを示します。
  
|**オプション**|**目的**|**実行方法**|
|:-----|:-----|:-----|
|閉じる  <br/> |表示を閉じますが、ユーザー ID で識別された Skype for Business セッションは引き続き実行できます。 これにより、引き続き通知を受け取り、他のユーザーとやり取りすることができます。 <br/> <br/> 画面の下部にあるタスク バーまたは通知領域の Skype for Business アイコンをクリックすると、いつでも表示を取得できます。  <br/> | Skype for Business のメイン ウィンドウで、次のいずれかの操作を行います。 <br/> 1. [オプション] ボタン **を選択** し、[ファイルを閉じる]**を選択**  >  **します**。  <br/> 2. ウィンドウ **の右上隅** にある [閉じる] ボタン (X) をクリックします。 <br/> |
|サインアウト  <br/> |ユーザー ID に関連付けられているセッションを終了しますが、Skype for Business はバックグラウンドで引き続き実行されます。 サインアウトすると、サインイン ウィンドウが表示されます。  <br/> **ヒント:** サイン **アウト時に [サインイン情報を** 削除する] を選択して、コンピューターからログオン ID とパスワードのレコードを削除します。 これにより、サポートユーザーがサインインの問題を簡単にトラブルシューティングできます。 また、承認されていないユーザーが資格情報を使用してログオンするのが難しくなるので、サインイン情報のセキュリティを高めることができます。 <br/> |Skype for Business のメイン ウィンドウで、[オプション] ボタンを選択し、[ファイルのサインアウト  >  **] を選択します**。  <br/> |
|Exit  <br/> |Skype for Business セッションを終了し、コンピューターで Skype for Business をシャットダウンします。 終了した後、再起動する場合は、Skype for Business で [すべてのプログラム>  >  選択します。 <br/> |Skype for Business のメイン ウィンドウで、[オプション] ボタンを **選択し、[** ファイルの終了]**を選択**  >  **します**。  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>スマート カードを使用して Skype for Business にサインインする

一部の組織では、ユーザーのセキュリティを強化するために、2 要素認証と呼ばれる複数ステップのサインイン プロセスを使用しています。 このオプションを使用する場合は、Skype for Business にサインインするための "スマート カード" が必要です。 スマート カードは、物理カードまたは仮想カードのいずれかです。
  
- **物理** クレジット カードのサイズについて。 ログイン時にスマート カード リーダーに挿入します。
    
- **仮想** 物理オブジェクトではなく、コンピューター上の特別なチップに書き込まれる電子識別子です。本質的には、スマート カードがコンピューターに組み込まれます。 TPM (トラステッド プラットフォーム モジュール) Windows 8コンピューターでのみ使用できます。
    
### <a name="enroll-your-smart-card"></a>スマート カードを登録する

スマート カードでサインインする前に、カードを "登録" する必要があります。つまり、ユーザー資格情報をカードで識別する必要があります。 カードが物理カードか仮想カードかは、この場合です。 このプロセスは、Skype for Business Server 管理者によって既に実行されている可能性があります。 それが完了したかどうか不明な場合は、確認してください。
  
> [!NOTE]
> 各仮想スマート カードは、それがインストールされているデバイスにのみ関連付けられているので、使用する各仮想スマート カードに個別のカードを登録Windows 8必要があります。 
  
### <a name="to-manually-enroll-your-smart-card"></a>スマート カードを手動で登録するには

1. Skype for Business を実行するコンピューターにログオンします。
    
2. このInternet Explorer、組織の証明機関 Web 登録ページに移動します。 
    
    このリソースが存在しない場合は、Skype for Business Server 管理者にこのリソースの Web アドレスを問い合わせてください。 URL は次のように表示されます。 https://MyCA .[yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Internet Explorer 10 を使用している場合は、この Web サイトを互換モードで表示する必要があります。 
  
3. 認定ページにログオンするように求めるメッセージが表示されたら、(コンピューターの管理者としてではなく) ドメイン アカウントを使用してログオンします。
    
4. Web サイトのウェルカム ページで、[証明書の要求 **] を選択します**。
    
5. [高度 **な要求] を選択します**。
    
6. Select **Create and submit a request to this CA,** then click **Next**.
    
7. これで、スマート カード登録ステーションというページが表示されます。 ActiveX コントロールをインストールする要求を承認し、次のように [証明書の要求の詳細設定] フォームに入力します。
    
    a.  [ **証明書テンプレート] ドロップダウン** リスト **から [Smartcard** ユーザー] を選択します。
    
    b. [新 **しいキー セットの作成] を選択します**。
    
    c. スマート カードのラベルで製造元の情報を見つけ **、CSP** のドロップダウン リストからその製造元を選択します。
    
    d.  CSP **を** 要求形式として選択します (まだ選択されていない場合)。
    
    e.  まだ選択されていない場合は、[ハッシュ アルゴリズム] ドロップダウン リストから **sha1** を選択します。
    
    f. 証明書に認識される名前を付け、[送信] をクリック **します**。
    
8. 次に、登録ステーションに接続されているカード リーダーに空白のスマート カードを挿入し、[登録] をクリック **します**。
    
9. メッセージが表示されたら、暗証番号 (PIN) を入力し **、[OK]** をクリックします。
    
    > [!NOTE]
    > テクニカル サポート担当者からスマート カードの登録に使用する特別な PIN が提供されていない場合は、既定のスマート カード PIN 値 (12345678) を使用します。 
  
10. スマート カードを初めて使用する場合にユーザーに PIN の変更を強制するオプションを選択します。
    
11. 次に、登録ステーションに接続されているカード リーダーに空白のスマート カードを挿入し、[登録] をクリック **します**。
    
12. メッセージが表示されたら、暗証番号 (PIN) を入力し **、[OK]** をクリックします。
    
    > [!NOTE]
    > テクニカル サポート担当者からスマート カードの登録に使用する特別な PIN が提供されていない場合は、既定のスマート カード PIN 値 (12345678) を使用します。 
  
13. スマート カードを初めて使用する場合にユーザーに PIN の変更を強制するオプションを選択します。
    
14. **[OK]** をクリックして、表示される証明書に自分の情報が含されていないことを確認します。
    
15. 証明書が発行されたという通知が表示された後、[この証明書のインストール] をクリックして登録プロセスを完了します。
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>スマート カードの資格情報を使用して Skype for Business にサインインする

スマート カードを初めて使用する前に、Skype for Business のサインイン ページで [サインイン情報の削除] をクリックしてください。 これにより、コンピューターに保存されているサインイン資格情報が消去され、考えられるエラーの原因が排除されます。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>スマート カードの資格情報を使用して Skype for Business にサインインするには

1. Skype for Business クライアントを起動します。
    
2. [サインイン] 画面の [サインイン アドレス] ボックスにサインイン ユーザー アカウント名を入力し、[サインイン] を **クリックします**。
    
3. 仮想スマート カードを使用している場合は、この手順を省略します。
    
    物理スマート カードを使用している場合は、スマート カードリーダーにスマート カードを挿入し、入力を求めるメッセージを表示して、カードが検出されたら **[OK]** をクリックします。
    
4. スマート カードの PIN 番号を入力し **、[OK]** をクリックします。
    
    > [!NOTE]
    > サポート担当者によってスマート カードの PIN 番号が割り当てられていない場合は、既定値である 12345678 を使用します。 
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で 2 要素認証を管理する](two-factor-authentication.md)
  
[Skype for Business Server で 2 要素認証を構成する](configure-two-factor.md)
