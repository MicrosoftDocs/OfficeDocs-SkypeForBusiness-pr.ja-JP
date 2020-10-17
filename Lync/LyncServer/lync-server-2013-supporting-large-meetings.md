---
title: 'Lync Server 2013: 大規模会議のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523924"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>Lync Server 2013 を使用した大規模会議のサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

大規模な会議には次の特性があるため、前のセクションで説明したテスト モデルは採用されません。

  - 会議の形式が一対多のプレゼンテーションである。

  - 1 人または少数のユーザーが発表者であり、他のユーザーは出席者として参加するだけである。

  - PowerPoint プレゼンテーションの共有が主なデータ グループ作業になる。

  - 音声が必要であり、ビデオも使用する場合がある。

  - 専任担当者 (通常は会議の開催者または開催者の補佐役) がかなり前から会議を設定する。

  - (発表者ではなく) 専任スタッフがオンライン会議への接続、音声、ビデオ、およびスライドの共有作業の確認、ロビーとユーザー ロールの管理、参加者のミュートおよびミュート解除、質問の受付、レコーディングの管理などを必要に応じて行い、会議を運営する。

最大 1,000 ユーザーの大規模な会議をサポートするには、共有ハードウェア モデルと予約なしモデルの両方に関する問題に対処する必要があります。

最大1000ユーザーの会議に十分な CPU およびメモリリソースを確保するには、ホストするフロントエンドサーバーが他のインスタントメッセージング (IM) とプレゼンスまたはエンタープライズ Voip ワークロードをホストしないようにする必要があります。 また、会議の規模に関係なく、他の会議をホストしないようにすることも必要です。 これは、最大1000ユーザーの会議をホストするために、最大で1000ユーザーの大規模な会議をホストする専用の Lync Server プールを個別に設定する必要があることを意味します。

大規模な会議をホストするための専用の Lync Server プールでは、1つの会議のみを同時に1000ユーザーまでホストする必要があるため、会議の時間は、フロントエンドサーバーから専用にサポートするために、アウトバンドのスケジューリングプロセスによって事前に予約されている必要があります。 一度に複数の大規模な会議をサポートする場合は、専用の大規模会議プールを複数設定することをお勧めします。

大規模な会議のオンライン部分は専任担当者が実行し、監視することをお勧めします。この担当者は、組織の設定に応じて、開催者、開催者または発表者の代理人、大規模な会議の専任サポート チームのメンバーのいずれでもかまいません。

次のセクションでは、大規模な会議のための専用プールを実装する方法について説明します。これには、Lync Server 2013 を使用して大規模な会議のシナリオをサポートするためのベストプラクティスが含まれます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での大規模会議のサポートの設定](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Lync Server 2013 での大規模な会議の管理](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

