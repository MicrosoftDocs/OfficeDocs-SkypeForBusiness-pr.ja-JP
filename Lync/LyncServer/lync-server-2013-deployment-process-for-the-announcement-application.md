---
title: 'Lync Server 2013: アナウンスアプリケーションの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44fc32360fe7ffe1924fbc663709dd1f41cf4a36
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のアナウンスアプリケーションの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

このセクションでは、アナウンスメントアプリケーションの展開に必要な手順の概要について説明します。 アナウンスを構成する前に、エンタープライズ Voip を展開する必要があります。 [] エンタープライズ Voip を展開すると、アナウンスメントアプリケーションに必要なコンポーネントがインストールされ、有効になります。

### <a name="announcement-deployment-process"></a>アナウンスの展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>ロール</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アナウンス設定を構成する</p></td>
<td><ul>
<li><p>音声ファイルを録音およびアップロードするか、音声合成 (TTS) を使用してアナウンスを作成します。</p></li>
<li><p>割り当てられていない番号の範囲を構成し、適切なアナウンスに関連付けます。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でアナウンスを作成する</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013 で割り当てられていない番号の表を構成する</a></p></td>
</tr>
<tr class="even">
<td><p>アナウンスの展開の確認</p></td>
<td><p>アナウンスを聞いてテストし、構成が予想どおりに動作することを確認します。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">オプションLync Server 2013 でのアナウンスの展開の確認</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

