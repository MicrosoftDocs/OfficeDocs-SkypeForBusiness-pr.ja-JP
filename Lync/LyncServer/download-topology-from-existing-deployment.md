---
title: 既存の展開環境からトポロジをダウンロードする
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 903b115eaa820245135e0bc2c3650ba596c5d925
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502904"
---
# <a name="download-topology-from-existing-deployment"></a>既存の展開環境からトポロジをダウンロードする

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-29_

Lync Server 2013 プールを作成する場合は、Lync Server 2010 に関連付けられている中央管理ストアを使用します。 初めてトポロジ ビルダーを起動して、その後、編集セッションを行う場合、トポロジ ビルダーに現在の構成ドキュメントを読み込ませる場所を指定するようメッセージが表示されます。 既に Lync Server 2010 トポロジが定義されており、中央管理ストアが確立されているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジ ビルダーは、データベースを読み取り、現在の定義を取得します。

**既存の展開環境からトポロジをダウンロードするには**

1.  [**Lync Server 展開ウィザード**] を開きます。

2.  [**Lync Server 2013 – 展開ウィザード**] ページで、[**管理ツールのインストール**] をクリックします。

3.  トポロジビルダーを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft Lync Server 2013** ]、[ **lync server トポロジビルダー**] の順にクリックします。

4.  [**既存の展開からトポロジをダウンロードする**] をクリックします。
    
    ![展開ウィザードのトポロジビルダーの設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "展開ウィザードのトポロジビルダーの設定")

5.  ファイル名を選択して、既定のファイルの種類である .tbxml でトポロジを保存します。

6.  示されているように、Lync Server ノードを展開して、展開に含まれるさまざまなサーバーの役割を表示させます。
    
    ![トポロジビルダーサーバーの役割全般プロパティ](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "トポロジビルダーサーバーの役割全般プロパティ")

</div>

<span> </span>

</div>

</div>

</div>

