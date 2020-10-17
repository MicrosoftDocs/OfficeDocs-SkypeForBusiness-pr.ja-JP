---
title: 'Lync Server 2013: 新しいクライアントバージョンポリシールールを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 732113537b79ad2ac767f64b861f296be508899c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512724"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Lync Server 2013 で新しいクライアントバージョンポリシールールを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-21_

クライアントバージョンポリシールールは、ユーザーが特定のクライアントおよびクライアントバージョンでログオンしようとしたときに実行する必要のあるアクションを定義します。 Lync Server 2013 コントロールパネルから、クライアントバージョンポリシーの個々のルールを作成または変更することができます。

<div>


> [!IMPORTANT]  
> 規則は優先順位に従って一覧表示されます。 たとえば、バージョン1.5 を実行しているクライアントの接続を許可するルールがあり、その後に2.0 より前のバージョンを実行しているクライアントをブロックするルールがある場合は、最初のルールが優先され、バージョン1.5 を実行しているクライアントは接続を許可されます。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してクライアントバージョンポリシールールを作成または変更するには

1.  Lync server コントロールパネルを使用して[、Lync server 2013 で新しいクライアントバージョンポリシーを作成または変更](lync-server-2013-create-or-modify-a-new-client-version-policy.md)します。

2.  [ **クライアントバージョンポリシーの編集** ] ページで、次のいずれかの操作を行います。
    
      - [ **新規** ] をクリックして、新しいクライアントバージョンルールを作成します。
    
      - 一覧から定義済みのクライアントの種類のいずれかをクリックし、[ **詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ワイルドカードを使用して、クライアントの種類を指定できます。

    
    </div>

3.  [ **ユーザーエージェント**] で、クライアントの種類を選択します。

4.  [ **バージョン番号**] で、次の操作を行います。
    
      - [ **メジャーバージョン**] に、クライアントのメジャーリリースに対応する番号を入力します。
    
      - [ **マイナーバージョン**] に、クライアントのマイナーリリースに対応する番号を入力します。
    
      - [ **ビルド**] に、クライアントのメジャーおよびマイナーリリースに対応する番号を入力します。
    
      - [ **更新**] に、更新されたクライアントのリリースに対応する番号を入力します。
    
    <div>
    

    > [!NOTE]  
    > ワイルドカードを使用してクライアントバージョン番号を示すことができます。

    
    </div>

5.  前の手順で指定したクライアントバージョンに一致する操作を指定するには、[ **比較操作**] で、次のいずれかをクリックします。
    
      - **同じ**
    
      - **異なる**
    
      - **より新しい**
    
      - **以上**
    
      - **より古い**
    
      - **以前**

6.  前の手順の条件が満たされたときに実行するアクションを指定するには、[ **アクション**] で次のいずれかをクリックします。
    
      - クライアントのログオンを許可するには、[ **許可**] をクリックします。
    
      - クライアントが Windows Server Update Service または Microsoft Update からの更新を送受信できるようにするには、[ **許可およびアップグレード**] をクリックします。 このアクションは、ユーザーエージェント **OC** が選択されている場合にのみ使用できます。
        
        <div>
        

        > [!NOTE]  
        > このアクションを選択すると、ユーザーが次回 Lync 2013 にサインインしたときに通知が表示されます。 この通知では、更新プログラムがある場合、Windows Server Update Service または Microsoft Update にまだリリースされていなくても、更新プログラムを利用できることが伝えられます。 混乱を避けるため、このアクションは更新プログラムが利用できるようになった後でのみ選択する必要があります。

        
        </div>
    
      - クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示できるようにするには、[ **URL を使用**して許可する] をクリックします。 この手順の後半で、URL を指定します。
    
      - クライアントのログオンを禁止するには、[ **ブロック**] をクリックします。
    
      - クライアントが Windows Server Update Service または Microsoft Update からの更新プログラムを受信できるようにするには、クライアントのログオンを禁止し、[ **ブロックとアップグレード**] をクリックします。 このアクションは、ユーザーエージェント **OC** が選択されている場合にのみ使用できます。
    
      - クライアントのログオンを禁止し、別のクライアントバージョンをダウンロードする場所についてのメッセージを表示するには、[ **URL を使用**してブロックする] をクリックします。 この手順の後半で、URL を指定します。

7.  オプション前の手順で [URL を使用し **て許可** する] または [ **ブロックを url でブロック** する] をクリックした場合は、[ **url**] にメッセージに含めるクライアントのダウンロード url を入力します。

8.  [ **OK**] をクリックし、[ **確定**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

