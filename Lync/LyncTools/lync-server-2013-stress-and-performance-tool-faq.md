---
title: Lync Server 2013 ストレスおよびパフォーマンスツールの FAQ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509214"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a>Lync Server 2013 ストレスおよびパフォーマンスツールの FAQ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

<div>

## <a name="frequently-asked-questions"></a>よく寄せられる質問

ここでは、Lync Server 2013 ストレスおよびパフォーマンスツールに関してよく寄せられる質問をいくつか紹介します。

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a>LyncPerfTool.exe を運用環境で実行できますか?

この方法はお勧めしません。 このツールは、サーバーのパフォーマンス、セキュリティ、およびユーザーの操作に影響を与えます。

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a>ユーザーが初めてログオンしたとき。 サーバーがこのような高負荷で実行されている理由

ユーザーが初めてログオンしたときに、追加の操作が行われます。 その結果、Microsoft SQL Server バックエンドサーバーのパフォーマンスが低下します。 結果を測定する前に、すべてのユーザーにログを記録する短時間のテストを実行してから、クライアントを再起動することをお勧めします。 1秒あたり12人を超える同時ユーザーログオンセッションはサポートしていませんが、ハードウェア構成によって異なります。

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントのメモリが不足しています。 どうすればよいですか?

クライアントのメモリが不足している場合は、コンピューターごとのユーザー数を減らす必要があります。

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a>クライアントは、常に100% の CPU を消費します。 どうすればよいですか?

すべてのユーザーがログオンした後、クライアントが非常に高い CPU を使用して実行されている場合は、コンピューターごとのユーザー数を減らす必要があります。 高 CPU スパイクを使用できますが、維持されている場合は負荷を減らす必要があります。

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a>サーバー自体でツールを実行することはできますか?

いいえ。 このシナリオはサポートされておらず、バイナリの不一致が原因で失敗する可能性があります。 また、ポイントはサーバー上のリソース消費を測定することなので、ツールを実行すると、測定値は無意味になります。

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバー上または Microsoft Hyper-v Server 2008/2012 上で LyncPerfTool.exe を実行できますか。

はい。

</div>

<div>

## <a name="what-does-mpop-mean"></a>MPOP の意味

MPOP は、複数のプレゼンスポイントを表します。 これは、ユーザーが複数のコンピューターから Lync 2013 にログオンしているシナリオをシミュレートすることを目的としています。 LyncPerfTool.exe では、各エンドポイントが既定のプロファイルを使用していることに注意してください (つまり、プロファイルは2つのプレゼンス間で分割されていません)。

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>LyncPerfTool.exe を開始しましたが、何も起きていません。 どうなっているのですか。

ユーザーが接続しているかどうかを確認するには、クライアントの [アクティブなエンドポイントの合計数」カウンターを確認します。 ユーザーが接続していない場合は、Lync Server 2013 の構成を確認します。 通常、この問題は、サーバー名、ユーザーのプレフィックス、またはパスワードが正しくないことが原因で発生します。 外部クライアントでは、TargetServer 値としてアクセスプロキシを指定する必要があることに注意してください。 構成ファイルのポートを確認します。

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a>問題が発生していることをどのように確認できますか?

さまざまな LyncPerfTool パフォーマンスカウンターは、ユーザーが接続し、アクションを実行しているかどうかを示します。 ただし、Lync 2013 を使用して目的のアクションを実行することによって、アカウントの1つにログオンすることが簡単に確認できます。

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a>Live Communications Server 2007 R2 容量計画ツールまたは Lync Server 2010 がインストールされている。 これでよろしいですか。

いいえ。 相互運用性の問題があるため、この製品の以前のバージョンをすべてアンインストールする必要があります。

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>ストレスとパフォーマンスのツールによって、CAA 呼び出し情報サーバーのトポロジはセットアップされますか。

いいえ。 このツールは、ユーザー、連絡先、および配布リストを作成し、ユーザーの負荷をシミュレートします。

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールがサポートする最大ユーザー数はどのくらいですか?

これらのツールを使用して、合計8万のユーザーと実行される、3万ユーザーを合計してテストしました。 使用可能なクライアントとサーバーのハードウェアに応じて、技術上の制限により、より高い価値を実現できるということは、最大で12万のユーザーを推奨します。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

