---
title: 既存の展開環境からトポロジをダウンロードする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>既存の展開環境からトポロジをダウンロードする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-29_

Lync Server 2013 プールを作成する場合は、Lync Server 2010 に関連付けられている中央管理ストアを使用します。 最初の使用時と後続の編集セッションでトポロジビルダーを起動すると、トポロジビルダーで現在の構成ドキュメントを読み込む場所を確認するメッセージが表示されます。 既に Lync Server 2010 トポロジを定義しており、全体管理ストアを確立しているため、既存の展開からトポロジをダウンロードすることを選択する必要があります。 トポロジビルダーはデータベースを読み取り、現在の定義を取得します。

**既存の展開からトポロジをダウンロードするには**

1.  **Lync Server 展開ウィザード**を開きます。

2.  [ **Lync Server 2013-展開ウィザード**] ページで、[**管理ツールのインストール**] をクリックします。

3.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013** ]、[ **lync server Topology Builder**] の順にクリックします。

4.  [**既存の展開からトポロジをダウンロード**] を選択します。
    
    ![展開ウィザードのトポロジビルダーの設定](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "展開ウィザードのトポロジビルダーの設定")

5.  ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。

6.  表示されている [Lync Server] ノードを展開して、展開内のさまざまなサーバーの役割を表示します。
    
    ![トポロジビルダーサーバーの役割の全般プロパティ](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "トポロジビルダーサーバーの役割の全般プロパティ")

</div>

<span> </span>

</div>

</div>

</div>

