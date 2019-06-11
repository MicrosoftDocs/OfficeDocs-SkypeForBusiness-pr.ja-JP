---
title: 'Lync Server 2013: Office Web Apps サーバーの構成を検証する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Lync Server 2013 で Office Web Apps サーバーの構成を検証する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-22_

Office Web Apps サーバーをトポロジに追加した後で、そのトポロジが公開されると、Lync Server イベントログに2つの新しいイベントログイベントが表示されます。 最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。

**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になりました。**

これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。

**Web 会議サーバー Office Web Apps サーバー検出が成功しました。**

**Office Web Apps サーバーの内部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps サーバーの外部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Office Web Apps サーバーの検出に失敗したことを示す、イベント ID が41033の LS データ MCU イベントが表示される場合。 その場合、Microsoft Lync Server 2013 は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試します。 検出プロセスが繰り返し失敗する場合は、トポロジドキュメントから Office Web Apps サーバーを削除し、更新されたトポロジを公開して、接続の問題が解決した後で、Office Web Apps サーバーをトポロジに追加してみます。

Office Web Apps サーバーが正しく構成されていて、検出プロセスによって認識されている場合は、Microsoft Lync 2013 クライアントのペア間で PowerPoint プレゼンテーションを共有することで、Office Web Apps サーバーが正常に動作していることを確認できます。 ユーザー A が PowerPoint プレゼンテーションを読み込み、表示できる場合に、ユーザー B が会議に参加すると、そのプレゼンテーションが Office Web Apps サーバーで動作することを確認できます。

Office Web Apps サーバーが正しく構成されているように見えても、PowerPoint プレゼンテーションを共有しようとすると、"サーバーの接続に問題が発生したため、一部の共有機能を利用できません" というエラーメッセージが表示されることがあります。 このエラーメッセージが表示された場合は、新しい Office Web Apps サーバーに関連付けられたフロントエンドサーバー (またはサーバー) を再起動する必要があります。

</div>

<span> </span>

</div>

</div>

</div>

