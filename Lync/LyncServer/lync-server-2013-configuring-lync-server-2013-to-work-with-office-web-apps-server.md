---
title: Office Web Apps サーバーで動作するように Lync Server 2013 を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Office Web Apps サーバーで動作するように Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-04-22_

Lync Server 2013 で Office Web Apps サーバーを使用するように構成するには、Office Web Apps サーバーを展開して構成する必要があります。 1つの Office Web Apps サーバーをインストールして構成する方法について詳しくは、「office web apps サーバー**と office** web apps をインストールして構成する」を参照してください。または、Office Web Apps サーバーファームをインストールして構成する方法については、こちらを参照してください。使用.

Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成されたら、新しいサーバーと通信するために Lync Server を構成する必要があります。これは、Office Web Apps サーバー検出 URL を Lync Server トポロジに追加することによって行われます。 トポロジに Office Web Apps サーバーを追加するには、次の手順を行います。

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開からトポロジをダウンロードする**] を選択して [**OK**] をクリックします。

3.  [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。

4.  [トポロジビルダー] で、[ **Lync Server 2013**] を展開し、サイトの名前を展開し、[ **Enterprise Edition のフロントエンドプール**] を展開して、いずれかのプールの名前を右クリックし、[**プロパティの編集**] をクリックします。

5.  [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。

6.  [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
    Office Web Apps サーバーがオンプレミスで、Lync Server 2013 と同じネットワークゾーンにインストールされている場合は、[ **Office Web Apps サーバーを外部ネットワーク (つまり、境界/インターネット) に展開**する] オプションを選択しないでください。
    
    Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。

7.  [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。 Office Web Apps の検出 URL がプールの関連付けの1つとして表示されます。

Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。

トポロジに探索 URL を追加した後、この更新されたトポロジを公開する必要があります。 これを行うには、トポロジ ビルダーで次の操作を行います。

1.  [**操作**] をクリックし、[**トポロジの公開**] をクリックします。

2.  トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。

3.  [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。

4.  トポロジ ビルダーを閉じます。

</div>

<span> </span>

</div>

</div>

</div>

