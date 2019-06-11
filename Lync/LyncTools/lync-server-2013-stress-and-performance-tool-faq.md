---
title: Lync Server 2013 のストレスとパフォーマンスに関するツールについてよく寄せられる質問
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 のストレスとパフォーマンスに関するツールについてよく寄せられる質問

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>よく寄せられる質問

ここでは、Lync Server 2013 のストレスとパフォーマンスツールについてよく寄せられる質問を示します。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>LyncPerfTool を運用環境で実行できますか?

この方法はお勧めしません。 このツールは、サーバーのパフォーマンス、セキュリティ、ユーザーエクスペリエンスに影響を与えます。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>ユーザーに初めてログオンしています。 サーバーが高負荷で実行されているのはなぜですか?

ユーザーが初めてログオンしたときは、その他の操作が行われます。 その結果、Microsoft SQL Server バックエンドサーバーのパフォーマンスが低下します。 すべてのユーザーにログを記録する短いテストを実行してから、結果を測定する前にクライアントを再起動することをお勧めします。 1秒あたり12回の同時ユーザーログオンセッションはサポートされませんが、これはハードウェア構成によって異なります。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントでメモリが不足しています。 どうしたらいいでしょう。

クライアントのメモリが不足している場合は、コンピューターあたりのユーザー数を減らす必要があります。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>クライアントは、常に 100% の CPU を搭載しています。 どうしたらいいでしょう。

すべてのユーザーがログオンした後でクライアントが非常に高い CPU で実行されている場合は、コンピューターあたりのユーザー数を減らす必要があります。 CPU のスパイクの増加は許容されていますが、持続する場合は、読み込みを減らす必要があります。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>サーバー自体でツールを実行できますか?

いいえ。 このシナリオはサポートされていないため、バイナリの不一致のために失敗することがあります。 また、ポイントはサーバー上のリソース消費量を測定するため、ツールを実行すると、測定の意味がありません。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバーまたは Microsoft Hyper-v Server 2008/2012 で LyncPerfTool を実行できますか?

はい。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP は何を意味していますか?

MPOP は、複数のプレゼンスポイントを表します。 これは、ユーザーが複数のコンピューターから Lync 2013 にログオンしているシナリオをシミュレートすることを目的としています。 LyncPerfTool では、各エンドポイントが既定のプロファイルを使用していることに注意してください (つまり、プロファイルは2つのプレゼンス間で分割されません)。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>LyncPerfTool を開始しましたが、何も起こりません。 どうなっているのですか。

クライアントの [アクティブなエンドポイントの合計数カウンターを確認して、ユーザーが接続しているかどうかを確認します。 ユーザーが接続していない場合は、Lync Server 2013 の構成を確認します。 この問題は、サーバー名、ユーザーのプレフィックス、またはパスワードが正しくないことが原因で発生します。 外部クライアントでは、TargetServer 値としてアクセスプロキシを指定する必要があることに注意してください。 構成ファイルでポートを確認します。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>何が起こっているかを知る方法を教えてください。

さまざまな LyncPerfTool パフォーマンスカウンターは、ユーザーが接続して操作を実行しているかどうかを示します。 ただし、Lync 2013 を使用して、必要な操作を実行して、アカウントの1つにログオンすることを簡単に確認できます。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Live Communications Server 2007 R2 キャパシティプランニングツールまたは Lync Server 2010 がインストールされています。 よろしいですか?

いいえ。 相互運用性の問題があるため、この製品の以前のバージョンをすべてアンインストールする必要があります。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>ストレスとパフォーマンスのツールで CAA を Call Information server topology をセットアップしますか?

いいえ。 このツールでは、ユーザー、連絡先、配布リストが作成され、ユーザーロードがシミュレートされます。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールでサポートされるユーザーの最大数は何人ですか?

これらのツールを使用して、最大で8万ユーザーを作成し、合計3万ユーザーを実行しました。 使用できるクライアントとサーバーのハードウェアによっては、最大で12万のユーザーを対象としていますが、技術的な制限により、高い価値を実現することができます。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

