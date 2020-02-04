---
title: 'Lync Server 2013: スマートカード認証のためにユーザーを登録する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013 でスマートカード認証のユーザーを登録する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-03_

スマート カードの認証を行うユーザーを登録する方法は、主に 2 つあります。Web 登録を使ってスマート カード認証のユーザーを直接登録する方法がより簡単で、登録エージェントを使う方法はより複雑です。このトピックでは、スマート カードの証明書を自分で登録する方法について説明します。

登録エージェントとしてユーザーの代理として登録する方法について詳しくは、「他のユーザー [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)の代理で証明書を登録する」をご覧ください。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>スマート カードの認証を行うユーザーを登録するには、次の操作を行います。

1.  Lync 対応ユーザーの資格情報を使用して、Windows 8 ワークステーションにログインします。

2.  Internet Explorer を起動します。

3.  **証明機関の Web 登録**ページを参照しますhttps://MyCA.contoso.com/certsrv)(例:
    
    <div>
    

    > [!NOTE]  
    > Internet Explorer 10 を使っている場合は、この Web サイトを互換モードで見る必要がある場合があります。

    
    </div>

4.  Web サイトの [**ようこそ**] ページで、[**証明書の要求**] を選びます。

5.  次に、[**証明書の要求の詳細設定**] を選びます。

6.  [**この CA への要求を作成し送信する。**] を選びます。

7.  [**証明書のテンプレート**] セクションで [**スマート カード ユーザー**] を選び、[証明書の要求の詳細設定] を次のように入力します。
    
      - [**キーのオプション**] で次の設定を確認します。
        
          - [**新しいキー セットを作成する**] ラジオ ボタンを選ぶ
        
          - [**CSP**] で、[**Microsoft ベース スマート カード暗号化プロバイダー**] を選ぶ
        
          - [**キー使用法**] で、[**Exchange**] を選ぶ (このオプションのみ有効)
        
          - [**キーのサイズ**] に、**2048** と入力する
        
          - [**自動キー コンテナー名**] が選択されている
        
          - その他のボックスはオフにします。
    
      - [**追加オプション**] で次の値を確認します。
        
          - [**要求の形式**] で [**CMC**] を選ぶ。
        
          - [**ハッシュ アルゴリズム**] で [**sha1**] を選ぶ。
        
          - [**フレンドリ名**] に「**Smardcard Certificate**」と入力する。

8.  物理カード リーダーを使っている場合は、デバイスにスマート カードを挿入します。

9.  [**送信**] をクリックして証明書要求を送信します。

10. 入力を求められたら、仮想スマート カードを作成したときに使った PIN を入力します。
    
    <div>
    

    > [!NOTE]  
    > 仮想スマート カードの既定の PIN の値は、「12345678」です。

    
    </div>

11. 証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。
    
    <div>
    

    > [!NOTE]  
    > 「証明書の要求の生成はこの Web ブラウザーではサポートされていません。」というエラーが発生して証明書の作成が失敗した場合、解決する方法として次の 3 つが考えられます。 
    > <OL>
    > <LI>
    > <P>Internet Explorer の [互換表示] を有効にする</P>
    > <LI>
    > <P>Internet Explorer で [イントラネットの設定を有効にする] オプションを有効にする</P>
    > <LI>
    > <P>Internet Explorer の [インターネット オプション] の [セキュリティ] タブで、[すべてのゾーンを既定のレベルにリセットする] を選ぶ</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

