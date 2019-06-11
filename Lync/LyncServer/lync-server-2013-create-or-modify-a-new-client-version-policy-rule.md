---
title: 'Lync Server 2013: 新しいクライアントのバージョンポリシールールを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Lync Server 2013 で新しいクライアントのバージョンポリシールールを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-21_

クライアントのバージョンポリシールールは、ユーザーが特定のクライアントとクライアントバージョンでログオンしようとしたときに実行される操作を定義します。 Lync Server 2013 コントロールパネルからクライアントのバージョンポリシーの個々のルールを作成または変更することができます。

<div>


> [!IMPORTANT]  
> ルールは優先順位の順に一覧表示されます。 たとえば、バージョン1.5 を実行しているクライアントに対して接続を許可するルールがあり、その後に2.0 より前のバージョンを実行しているクライアントをブロックするルールがある場合は、最初のルールが優先され、バージョン1.5 を実行しているクライアントで接続が許可されます。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Lync Server コントロールパネルでクライアントのバージョンポリシールールを作成または変更するには

1.  Lync server 2013 で Lync Server コントロールパネルを使用して[、新しいクライアントバージョンポリシーを作成または変更](lync-server-2013-create-or-modify-a-new-client-version-policy.md)します。

2.  [**クライアントのバージョンポリシーの編集**] ページで、次のいずれかの操作を行います。
    
      - [**新規**] をクリックして、新しいクライアントバージョン規則を作成します。
    
      - リストで定義されているクライアントの種類のいずれかをクリックし、[**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > ワイルドカードを使用して、クライアントの種類を示すことができます。

    
    </div>

3.  [**ユーザーエージェント**] で、クライアントの種類を選択します。

4.  [**バージョン番号**] で、次の操作を行います。
    
      - [**メジャーバージョン**] に、クライアントのメジャーリリースに対応する番号を入力します。
    
      - [**マイナーバージョン**] に、クライアントのマイナーリリースに対応する番号を入力します。
    
      - [**ビルド**] に、クライアントのメジャーとマイナーのリリースに対応する番号を入力します。
    
      - [ **Update**] に、更新されたクライアントのリリースに対応する番号を入力します。
    
    <div>
    

    > [!NOTE]  
    > クライアントのバージョン番号を示すには、ワイルドカードを使用できます。

    
    </div>

5.  前の手順で指定したクライアントのバージョンに対して一致する操作を指定するには、**比較操作**で次のいずれかをクリックします。
    
      - **[同じ]**
    
      - **[等しくない]**
    
      - **[より新しい]**
    
      - **[より新しいか同じ]**
    
      - **[より古い]**
    
      - **[より古いか同じ]**

6.  前の手順の条件が満たされたときに実行する操作を指定するには、次の**操作**のいずれかをクリックします。
    
      - クライアントがログオンできるようにするには、[**許可**] をクリックします。
    
      - クライアントが Windows Server Update Service または Microsoft Update からの更新プログラムをログオンして受信できるようにするには、[**許可/アップグレード**] をクリックします。 この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。
        
        <div>
        

        > [!NOTE]  
        > このアクションを選ぶと、次回ユーザーが Lync 2013 にサインインしたときに通知が表示されます。 この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。 混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。

        
        </div>
    
      - クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示できるようにするには、[ **URL で許可**] をクリックします。 この手順の後半で、URL を指定します。
    
      - クライアントがログオンしないようにするには、[**ブロック**] をクリックします。
    
      - クライアントがログオンし、Windows Server Update Service または Microsoft Update から更新プログラムを受信できるようにするには、[**ブロックとアップグレード**] をクリックします。 この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。
    
      - クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示するには、[ **URL を含むブロック**] をクリックします。 この手順の後半で、URL を指定します。

7.  省略前の手順で [URL を指定して**許可**] または [ **Url を含むブロック**] をクリックした場合は、クライアントのダウンロード url を入力して、 **url**のメッセージに含めることができます。

8.  [ **OK**] をクリックし、[**コミット**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

