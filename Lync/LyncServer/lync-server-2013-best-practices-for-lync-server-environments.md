---
title: 'Lync Server 2013: Lync Server 環境のベストプラクティス'
description: 'Lync Server 2013: Lync Server 環境のベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae6c02621bd6506d2a1d379aeaf92b20ce3f7ae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552213"
---
# <a name="best-practices-for-lync-server-2013-environments"></a>Lync Server 2013 環境のベストプラクティス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-04_

システムの実行中の操作には、次の一般的な原則を適用する必要があります。

  - MOF を理解**して活用**     するMOF は、ベストプラクティス、原則、およびモデルの集合であり、毎日の Lync Server 2013 操作などの IT 資産の管理に関する技術的なガイダンスを組織に提供します。 MOF の次のガイドラインは、Microsoft 製品のミッションクリティカルな運用システムの信頼性、可用性、サポート性、および管理性を実現するのに役立ちます。 詳細については、「 [Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)」を参照してください。

  - **Lync Server 2013 のベストプラクティスについて説明**     します。Lync Server 2013 を管理するための実用的かつ実証済みの手順を実装することをお勧めします。 「試行」、「テスト済み」、およびドキュメントで文書化された操作を管理する方法は、独自の方法を開発するよりも効率的です。

  - **個別の操作を日単位、週単位、および月単位のプロセス**     に分けます。定期的に実行する必要な運用タスクを文書化します。 タスクの実行方法を文書化することで、新しいテクノロジが展開されたときや、スタッフの変更が発生したときなど、運用環境に変更があった場合に、情報が確実に保持されるようにすることができます。 タスクが毎日、毎週、毎月実行される管理可能なワークロードには、運用タスクを分離することをお勧めします。 日常のタスクでは、システムの機能に焦点を当てることができます。また、月単位のタスクでは、システムの長期的な正常性を確保することに重点を置いています。
    
    このドキュメントは、エンタープライズ Voip を使用したインスタントメッセージング/プレゼンス (IM/P) コンポーネントまたは IM/P のみを展開する環境で使用できます。 タスクまたはチェックリストのアイテムがエンタープライズ Voip に固有のものである場合は、このことが説明されています。環境にエンタープライズ Voip が含まれていない場合は、部分をスキップすることができます。

  - **Lync Server 2013**     の運用に必要なツールを展開するさまざまなツールを使用して、問題のトラブルシューティングを行ったり、タスクを自動化したり、Lync Server 2013 環境の監視および保守に役立てることができます。 組織に対して標準のツールセットを定義することで、運用チームによって実行されるタスクが正確かつ効率的に、一貫して、制御された方法で実行されるようになります。 また、インシデントおよび主要な構成の変更を追跡するためのプロセスも実装する必要があります。

<div>

## <a name="reference"></a>リファレンス

一般にサーバーの管理の基本事項を理解していない読者のために、サーバーの管理方法の概要を説明します。 サーバー管理に精通している読者は、このセクションをスキップすることを選択できます。

ベストプラクティスは、IT 担当者が多くの環境で得た知識と経験に基づく推奨事項です。 これらは、Lync Server 管理者が毎日実行する必要のある一般的なタスクの標準的な手順を提供し、Lync Server 環境の管理に使用する必要があるツールを一覧表示します。

Lync 管理者の一般的なタスクには、次のようなものがあります。

  - **容量と可用性の管理**    今後の容量要件を予測し、システムの容量、信頼性、および可用性に関するレポートを作成するために、測定する方法と内容を定義します。 Lync Server を実行しているサーバーがシステムの負荷を処理するように設定されていること、および予定外のダウンタイムがサービスレベル契約 (SLA) で定義されているレベルの下に保持されていることを確認する必要があります。 さらに、定義された要件を引き続き満たすようにハードウェアをアップグレードする必要があります。

  - **変更管理および構成管理**    IT システムに加えられた変更を制御します。 これには、テスト、アプリケーションのフィードバックとコンティンジェンシー計画、すべての変更のドキュメント、および問題が発生した場合の管理からの承認を含める必要があります。 ソフトウェアおよびハードウェアアセットとその構成の記録を保持します。

  - **システム管理**    データベース管理、サイト管理などの管理タスクを実行するための標準的な方法の概要を示します。

  - **セキュリティ管理**    データの機密性、データの整合性、および IT インフラストラクチャのデータ可用性を保護するための詳細なポリシーと計画を立てます。 これには、IT セキュリティインフラストラクチャのメンテナンスと調整に関連する日常業務とタスクが含まれます。

  - **システムのトラブルシューティング**    今後同様の問題が発生しないようにするための手順を含む、予期しない問題を処理するためのアウトライン方法。

  - **サービスレベル契約**    IT システムのパフォーマンスに関する一連の目標を維持し、これらの目標に対するパフォーマンスを定期的に測定します。

  - **ドキュメント**    構成情報や教訓など、標準的な手順をドキュメント化し、それらを必要とするスタッフメンバーが使用できるようにします。 構成の変更が行われた後、ドキュメントを更新します。

</div>

<div>

## <a name="related-sections"></a>関連情報

続行する前に、次のシステム操作に関するトピックを確認してください。

  - [Lync Server 2013 での容量と可用性の管理](lync-server-2013-capacity-and-availability-management.md)

  - [Lync Server 2013 での変更管理](lync-server-2013-change-management.md)

  - [Lync Server 2013 での構成管理](lync-server-2013-configuration-management.md)

  - [Lync Server 2013 のシステム管理](lync-server-2013-system-administration.md)

  - [Lync Server 2013 でのサービスレベル契約](lync-server-2013-service-level-agreements.md)

  - [Lync Server 2013 のドキュメント](lync-server-2013-documentation.md)

  - [Lync Server 2013 の標準手順](lync-server-2013-standard-procedures.md)

  - [Lync Server 2013 の緊急時の手順](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Microsoft Operations Framework 4.0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

