---
title: 'Lync Server 2013: Office Web Apps サーバーの構成の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1cabdf03250a056c2fedaeb41e1f6839aea75a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Lync Server 2013 での Office Web Apps サーバーの構成の検証

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-22_

Office Web Apps サーバーをトポロジに追加した後、そのトポロジが公開された後、Lync Server イベントログに2つの新しいイベントログイベントが表示されるはずです。 最初に、LS データ MCU イベント (イベント ID 41034) を追加する必要があります。このイベントは、Office Web Apps サーバーが検出されたことを報告します。

**Web 会議サーバー Office Web Apps サーバーが検出され、PowerPoint コンテンツが有効になっています。**

これに加えて、Office Web Apps Server URL を報告する別の LS Data MCU イベント (イベント ID 41032) が表示されます。たとえば、次のように表示されます。

**Web 会議サーバー Office Web Apps サーバーの検出が成功しました。**

**Office Web Apps サーバー内部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Office Web Apps サーバーの外部発表者ページ:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Office Web Apps サーバーの内部出席者ページ:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

イベント ID が 41033 の LS Data MCU イベントが表示された場合、Office Web Apps Server の検出が失敗したことを意味します。 その場合、Microsoft Lync Server 2013 は、新しく構成された Office Web Apps サーバーを検出するために必要な回数だけ試行します。 検出プロセスが繰り返し失敗する場合、Office Web Apps Server をトポロジー ドキュメントから削除し、更新されたトポロジーを公開し、接続の問題が解決された後に Office Web Apps Server をトポロジーに再度追加します。

Office Web Apps サーバーが正しく構成されており、探索プロセスで認識されている場合は、Microsoft Lync 2013 クライアントのペア間で PowerPoint プレゼンテーションを共有することによって、Office Web Apps サーバーが正常に機能していることを確認できます。 ユーザー A が PowerPoint プレゼンテーションを読み込んで表示でき、ユーザー B が会議に参加してそのプレゼンテーションを表示できる場合、Office Web Apps Server は機能しています。

Office Web Apps Server が正しく構成されているような場合でも、PowerPoint プレゼンテーションを共有する際に「サーバーの接続問題により、一部の共有機能が使用できません」というエラー メッセージを受け取ることがあります。このエラー メッセージを受け取った場合、新しい Office Web Apps Server に関連したフロントエンド サーバー (場合によっては複数) を再起動します。

</div>

<span> </span>

</div>

</div>

</div>

