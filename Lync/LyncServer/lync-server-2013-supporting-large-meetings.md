---
title: 'Lync Server 2013: 大規模な会議のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Lync Server 2013 を使用した大規模な会議のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

大規模な会議は、前のセクションで説明したテストモデルに従っていないため、次のような特徴があります。

  - 会議の形式が一対多のプレゼンテーションである。

  - 1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。

  - PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。

  - 音声が必要であり、ビデオも使用する場合がある。

  - 通常、会議の開催者または開催者のアシスタントのいずれかが、会議を事前に設定している専用のユーザー。

  - (発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。

最大1000ユーザーの大規模な会議をサポートするには、共有ハードウェアモデルと非予約モデルの両方に関連する問題に対処する必要があります。

最大 1,000 ユーザーの会議に対応できる十分な CPU リソースとメモリ リソースを確保するには、ホスト側のフロントエンド サーバーで、他のインスタント メッセージング (IM) とプレゼンスやエンタープライズ VoIP のワークロードを一切ホストしないようにする必要があります。 他の会議のサイズに関係なく、他の会議も主催する必要はありません。 つまり、最大1000ユーザーの会議を主催するには、1000ユーザーの大人数の会議を主催する専用の Lync Server プールを設定する必要があります。

大規模な会議のホスティング専用の Lync Server プールは、1人のユーザーに対して同時に最大1000人の会議を開催する必要があります。そのため、フロントエンドの Serv から専用のサポートを受けるためには、帯域外のスケジュール処理を通じて事前に会議時間を予約する必要があります。サー. 一度に複数の大きな会議をサポートするには、複数の専用の大規模な会議プールを設定することをお勧めします。

専用ユーザーが大規模な会議のオンラインの一部を実行して監視することをお勧めします。 この人は、組織の設定に応じて、開催者、開催者の代理人、または専用の大型会議のサポートチームのメンバーである場合があります。

以下のセクションでは、大規模な会議用の専用プールを実装する方法について説明します。これには、大規模な会議のシナリオをサポートするために Lync Server 2013 を使用するためのベストプラクティスが含まれます。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での大規模な会議のサポートの設定](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Lync Server 2013 での大規模な会議の管理](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

