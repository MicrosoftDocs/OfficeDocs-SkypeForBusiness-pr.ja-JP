---
title: 'Lync Server 2013: スマートカード認証のユーザーの登録'
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
ms.openlocfilehash: 9a157d5492378771cf40a6438bbf8672efd01412
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013 でのスマートカード認証のユーザーの登録

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-03_

通常、スマートカード認証のためにユーザーを登録する方法は2つあります。 簡単な方法では、ユーザーが web 登録を使用してスマートカード認証を直接登録する必要がありますが、より複雑な方法では登録エージェントを使用する必要があります。 このトピックでは、スマートカード証明書のセルフ登録に重点を置いて説明します。

登録エージェントとしてのユーザーの代理での登録の詳細については、「他のユーザーの[https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367)代理として証明書を登録する」を参照してください。

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>スマートカード認証を使用するようにユーザーを登録するには

1.  Lync が有効なユーザーの資格情報を使用して、Windows 8 ワークステーションにログインします。

2.  Internet Explorer を起動します。

3.  **証明機関の Web 登録**ページに移動しますhttps://MyCA.contoso.com/certsrv)(例:)。
    
    <div>
    

    > [!NOTE]  
    > Internet Explorer 10 を使用している場合は、この web サイトを互換モードで表示する必要がある場合があります。

    
    </div>

4.  [**ようこそ**] ページで、[**証明書の要求**] を選択します。

5.  次に、[**要求の詳細設定**] を選択します。

6.  [**この CA への要求を作成し送信**する] を選択します。

7.  [**証明書テンプレート**] セクションの [**スマートカードユーザー** ] を選択し、次の値を使用して詳細証明書の要求を完了します。
    
      - **キーオプション**次の設定を確認します。
        
          - [**新しいキーセットの作成**] ラジオボタンを選択します。
        
          - **CSP**の場合、[ **Microsoft 基本スマートカード暗号化プロバイダー** ] を選択します。
        
          - **キー使用法**については、[ **Exchange** ] を選択します (このオプションは使用できます)。
        
          - **キーサイズ**の場合は、 **2048**を入力します。
        
          - **自動キーコンテナー名**が選択されていることを確認する
        
          - その他のボックスはオフのままにします。
    
      - [**その他のオプション**] で、次の値を確認します。
        
          - **要求の形式**には、[ **CMC**] を選択します。
        
          - [**ハッシュアルゴリズム**] で [ **sha1**] を選択します。
        
          - **フレンドリ名**には、 **Smardcard 証明書**を入力します。

8.  物理スマートカードリーダーを使用している場合は、デバイスにスマートカードを挿入します。

9.  [ **Submit** ] をクリックして証明書要求を送信します。

10. メッセージが表示されたら、仮想スマートカードの作成に使用した PIN を入力します。
    
    <div>
    

    > [!NOTE]  
    > 既定の仮想スマートカードの PIN の値は ' 12345678 ' です。

    
    </div>

11. 証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。
    
    <div>
    

    > [!NOTE]  
    > 証明書の要求が失敗し、"この Web ブラウザーは証明書の要求の生成をサポートしていません" というエラーが発生した場合は、次の3つの方法で問題を解決できます。 
    > <OL>
    > <LI>
    > <P>Internet Explorer で互換表示を有効にする</P>
    > <LI>
    > <P>Internet Explorer で [イントラネット設定を有効にする] オプションを有効にする</P>
    > <LI>
    > <P>Internet Explorer の [オプション] メニューの [セキュリティ] タブで、[すべての領域を既定のレベルにリセットする] 設定を選択します。</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

