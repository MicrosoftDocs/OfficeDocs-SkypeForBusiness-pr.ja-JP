---
title: 'Lync Server 2013: バックアップと復元の戦略の確立'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元の戦略の確立

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-26_

Lync Server のバックアップと復元の計画を作成する前に、組織の目標に合った戦略を開発する必要があります。 効果的なバックアップと復元の戦略を策定するには、次のことを行う必要があります。

  - ビジネスの優先順位を確立します。

  - バックアップと復元の要件を特定します。

<div>

## <a name="establishing-business-priorities"></a>ビジネスの優先順位の確立

組織のビジネスの優先順位を評価します。一般に、ビジネスの主な優先順位のうちで、バックアップと復元の戦略に関係するものには以下があります。

  - 業務継続の要件

  - データの完全性

  - データの重要性

  - ポータビリティの要件

  - コストの制約

お客様と一緒に開発するサービスレベル契約 (Sla) を決定するための、これらのヘルプなどのビジネスニーズ。 サービス レベル アグリーメントはバックアップと復旧の戦略に大きな影響を及ぼします。

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>バックアップと復元の要件の特定

ビジネスの優先度とサービスレベル契約によって、Lync Server のバックアップと復元に関する組織の要件を決定することができます。 以下についての要件を特定し、文書化します。

  - **バックアップの頻度バックアップの**   頻度のベストプラクティスの詳細については、「 [Lync Server 2013 のバックアップと復元のベストプラクティス](lync-server-2013-best-practices-for-backup-and-restoration.md)」を参照してください。

  - **バックアップと復元のツール**   には、ツールを使用するユーザーと、どのコンピューターを使用するかが含まれます。 このトピックで説明されているツールおよび必要なアクセス許可の詳細については、「 [Lync Server 2013 のバックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)」を参照してください。ツールとアクセス許可。

  - **[バックアップの場所**   ] バックアップがローカルで保持されるかリモートで保持されるかを特定し、セキュリティとアクセシビリティを考慮に入れます。 バックアップに使用するメディアを指定します。

  - **ハードウェア要件およびソフトウェア要件**   バックアップと復元をサポートするために必要な、特定のコンポーネントおよびソフトウェアとネットワーク接続のバックアップの保存と復元のハードウェアなど、特定のハードウェア要件およびソフトウェア要件を特定し、文書化します。 ハードウェアとソフトウェアの要件を開発する際には、次に示すさまざまな復元シナリオを念頭に置いてください。

  - **復元シナリオ**   次のシナリオの復元プロセスを示します。
    
      - Lync Server プールで障害が発生します。 このシナリオでは、プール内の各サーバーを構築し直す必要があります。
    
      - Standard Edition サーバーでエラーが発生します。 このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直してデータベースを復元する必要があります。
    
      - 中央管理ストアの損失。 このシナリオでは、少なくとも、中央管理ストアを復元して発行する必要があります。
    
      - 中央管理ストアが正常に機能している場合、バックエンドサーバーは失われます。 このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直してデータベースを復元する必要があります。
    
      - Lync Server プールのメンバーであるサーバーで障害が発生します。 このシナリオでは、新しいコンピューターまたはクリーンな状態のコンピューターにサーバーを構築し直す必要があります。
    
      - ファイルストアが失敗します。 このシナリオでは、ファイル サーバーまたはファイル クラスターを復元する必要があります。
    
      - アーカイブ、監視、または常設チャットデータベースが失敗します。 このシナリオでは、データベースを作成し直す必要があり、組織にとって重要なデータの場合にはデータの復元も必要です。 Lync Server のバックアップと実行を取得するために、アーカイブ、監視、常設チャットデータは必要ありません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

