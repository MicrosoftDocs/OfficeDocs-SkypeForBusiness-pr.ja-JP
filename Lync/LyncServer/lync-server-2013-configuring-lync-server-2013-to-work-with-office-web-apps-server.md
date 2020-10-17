---
title: Office Web Apps サーバーで動作するように Lync Server 2013 を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd362d42dd3d2927b15ff567343c116209a67e7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517364"
---
# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Office Web Apps サーバーで動作するように Lync Server 2013 を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-04-22_

Office Web Apps サーバーを使用するように Lync Server 2013 を構成する前に、Office Web Apps サーバーを展開して構成する必要があります。 単一の Office Web Apps サーバーのインストールおよび構成方法、または高可用性を得るための Office Web Apps サーバー ファームのインストールおよび構成方法の詳細については、「**Office Web Apps サーバーおよび Office Web アプリを展開するためのガイド**」を参照してください。

Office Web Apps サーバーが正常にインストールされ、Web ファームが正しく構成された後、新しいサーバーと通信するように Lync Server を構成する必要があります。これを行うには、Office Web Apps サーバーの検出 URL を Lync Server トポロジに追加します。 Office Web Apps サーバーをトポロジに追加するには、次の手順を実行します。

1.  [ **スタート**]、[ **すべてのプログラム**]、[ **Microsoft lync Server 2013**]、[ **lync server トポロジビルダー**] の順にクリックします。

2.  [**トポロジ ビルダー**] ダイアログ ボックスで、[**既存の展開環境からトポロジをダウンロードする**] をクリックし、[**OK**] をクリックします。

3.  [**トポロジに名前を付けて保存**] ダイアログ ボックスで、トポロジ ドキュメントの名前 (例: **PreWebAppsServerTopology**) を [**ファイル名**] ボックスに入力し、[**保存**] をクリックします。新しいトポロジで問題が発生した場合、後でこのトポロジを取得して再発行できます。

4.  トポロジビルダーで、[ **Lync Server 2013**] を展開し、サイトの名前を展開します。次に、[ **Enterprise Edition フロントエンドプール**] を展開して、プールの名前を右クリックし、[ **プロパティの編集**] をクリックします。

5.  [**プロパティの編集**] ダイアログ ボックスの [**全般**] タブで、[**Office Web Apps サーバーの関連付け**] という見出しを探し、[**新規作成**] をクリックします (または、ドロップダウン リストから既存の Office Web Apps サーバーを選択します)。

6.  [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。
    
    Office Web Apps サーバーがオンプレミスでインストールされており、Lync Server 2013 と同じネットワークゾーンにある場合、オプションの **Office Web Apps サーバーは外部ネットワーク (境界/インターネット) に展開** されている必要があります。
    
    Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。

7.  [**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、[**OK**] をクリックし、[**プロパティの編集**] ダイアログ ボックスで [**OK**] をクリックします。Office Web Apps 検出 URL がプールの関連付けの 1 つとして表示されます。

Office Web Apps サーバーに関連付ける必要がある各プールに対してこのプロセスを繰り返す必要があります。

検出 URL をトポロジに追加した後、この更新されたトポロジを公開する必要があります。これを行うには、トポロジ ビルダーで次の操作を行います。

1.  [**操作**] をクリックし、[**トポロジの公開**] をクリックします。

2.  トポロジの公開ウィザードの [**トポロジの公開**] ページで、[**次へ**] をクリックします。

3.  [**公開ウィザードの完了**] ページで、[**完了**] をクリックします。

4.  トポロジ ビルダーを閉じます。

</div>

<span> </span>

</div>

</div>

</div>

