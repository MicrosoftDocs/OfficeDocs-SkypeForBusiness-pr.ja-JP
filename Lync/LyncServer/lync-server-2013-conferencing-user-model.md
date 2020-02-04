---
title: Lync Server 2013 会議のユーザーモデル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f517e6d3ea3a832c4331377fa49ef7e474377de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013 の会議ユーザーモデル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Lync Server 会議のユーザーモデルの重要な部分は、会議のサイズです。 (前のセクションで説明したように) 複数のデータポイントからデータを収集した後、次のことを決定しました。

  - ほとんどの会議は、実際にはわずか 4 ~ 6 人の参加者が開催する、共同作業の小さな会議です。

  - 会議の約80% は、参加者が20人を超えています。

  - 会議の99.98% は、参加者数が100を超えています。

会議のサイズに加えて、会議のユーザーモデルでは、次のようなさまざまな要因も考慮する必要があります。

  - **同時会議**   では、同時に複数のユーザーが会議に出席することが予想されますか?

  - **メディアミックス**   会議のユーザーによって使用されるメディアの種類。

  - **ユーザーの種類**   は、内部ユーザー、リモートユーザー、フェデレーションユーザー、匿名ユーザーですか。

  - **会議のランプアップ**   会議のすべてのユーザーが会議に参加するにはどのくらいの時間がかかりますか?

ユーザーモデルの詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

テストに使用する会議とユーザーの数を決定するには、次の操作を行いました。

  - 組織内のユーザーの合計数を取得しました (たとえば、8万ユーザー)。会議の同時実行率 (たとえば、すべてのユーザーの 5%) によって、同時に会議に参加していると予想されるユーザーの合計数 (この例では、5% のユーザー) を求めています。、4000ユーザー)。

  - フロントエンドサーバーあたりの会議出席者の推定数 (この例では、フロントエンドサーバーあたり500ユーザー) を決定するために、ユーザーの合計数を、展開の Lync Server 2013、フロントエンドサーバー (たとえば、8台) で割ります。

  - フロントエンドサーバーあたりのユーザー数を平均会議のサイズ (たとえば、4人のユーザー) で割って、フロントエンドサーバーあたりの会議の推定平均数 (この例では、フロントエンドサーバーあたり125会議) を決定します。

  - 各フロントエンドサーバーでメディアのロードを1つずつ取得するために、メディアミックスを見積もりました。 たとえば、会議の75% が必要なのは、音声サポートだけでなく、会議の50% ではアプリケーション共有が必要であると想定した場合、47会議と188ユーザーは、各フロントエンドサーバーに同時に接続して、アプリケーション共有を行うことができます。

  - サーバーのスケーラビリティを確保するために、さまざまな会議サイズ (共有プールの最大250ユーザーのユーザーモデルに基づく) をテストしました。

</div>

<span> </span>

</div>

</div>

</div>

