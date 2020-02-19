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
ms.openlocfilehash: fa7cc640f0ed6ae4de2c0b8b25b83a3ec6bb89bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013 の会議のユーザーモデル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

Lync Server 会議のユーザーモデルの重要な部分は、会議のサイズです。 (前のセクションで説明したように) 複数のデータ ポイントからデータを収集したところ、次のことが明らかになりました。

  - ほとんどの会議は、実際には参加者が平均 4 ～ 6 人の小規模なグループ作業の会議です。

  - 会議の約 80% は参加者が 20 人未満です。

  - 会議の 99.98 % は参加者が 100 人未満です。

会議サイズに加えて、会議ユーザー モデルでは次のようなさまざまな要素も考慮します。

  - **同時会議**   会議に同時に何人のユーザーがいると予想されるか。

  - **メディア混合**   会議でユーザーが使用することが予想されるメディアの種類を指定します。

  - **ユーザーの種類**   は、内部ユーザー、リモートユーザー、フェデレーションユーザー、匿名ユーザーのいずれかです。

  - **会議のランプアップ時間**   会議のすべてのユーザーが会議に参加するまでにかかる時間を教えてください。

ユーザーモデルの詳細については、「 [Lync Server 2013 のユーザーモデル](lync-server-2013-user-models.md)」を参照してください。

テストに使用する会議およびユーザーの数を決定するため、次のことを行いました。

  - 組織内のユーザーの総数 (例: ユーザー数 80,000) を取得し、それに会議の同時割合 (例: すべてのユーザーの 5%) をかけて、会議に同時に参加すると予想されるユーザーの総数を決定しました (この例では、ユーザー数は 4000)。

  - フロントエンドサーバーあたりの会議参加者の推定数 (この500例では、1台のフロントエンドサーバー) を決定するために、ユーザーの合計数を Lync Server 2013、展開内のフロントエンドサーバーの数 (たとえば、8台のサーバー) で割る。

  - フロントエンドサーバーあたりのユーザー数を平均会議のサイズ (たとえば、4ユーザー) で割ることにより、フロントエンドサーバーあたりの会議の推定平均数 (この例では、1つのフロントエンドサーバーあたり125会議) を決定します。

  - 各フロントエンドサーバーでメディア負荷の数を取得するには、メディアミックスを見積もります。 たとえば、会議の75% が、音声サポートだけでなく、その会議の50% ではアプリケーション共有が必要であると仮定した場合、アプリケーション共有のために各フロントエンドサーバーに対して、平均47会議と188ユーザーが同時に接続されます。

  - (共有プールの最大ユーザー数 250 のユーザー モデルに基づいて) さまざまな会議サイズをテストし、サーバーの拡張性を確保しました。

</div>

<span> </span>

</div>

</div>

</div>

