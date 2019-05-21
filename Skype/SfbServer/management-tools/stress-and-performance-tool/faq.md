---
title: Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 応力とパフォーマンスツールについてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスツールとパフォーマンスツールの実行時に表示される可能性がある behaviours の明確化に役立ちます。.
ms.openlocfilehash: 36bb3e05751bd69b747d84fa563347b29362ddd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299710"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 のストレスとパフォーマンスのツールについてよく寄せられる質問
 
Skype for Business 2015 応力とパフォーマンスツールについてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスツールとパフォーマンスツールの実行時に表示される可能性がある behaviours の明確化に役立ちます。.
  
 この FAQ では、Skype for Business Server 2015 のストレスとパフォーマンスツールについてよく寄せられる質問の一部について説明し、トラブルシューティングやツール構成の選択肢について説明します。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>LyncPerfTool を運用環境で実行できますか?

この方法はお勧めでき**ません**。 このツールは、プロダクションサーバーのパフォーマンス、セキュリティ、およびエンドユーザーエクスペリエンスに影響を与えます。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>ユーザーを初めてログインします。 サーバーで高負荷が発生しているのはなぜですか?

ユーザーが初めてログオンしたときは、バックグラウンドで追加の操作が行われます。 その結果、Microsoft SQL Server バックエンドサーバーのパフォーマンスが低下する可能性があります。 すべてのユーザーに対してログを記録する短いテストを実行してから、ツールを使用して結果の測定を開始する前に、クライアントを再起動することをお勧めします。 Skype for Business Server は1秒あたり12回の同時ユーザーログオンセッションをサポートしていませんが、サーバーで処理できる実際の番号はハードウェア構成によって異なり、サポートされている値よりも低い場合があります。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントでメモリが不足しています。 どうしたらいいでしょう。

クライアントでメモリが不足している場合は、Skype for Business Server フロントエンドプールごとにログオンしているユーザー数を減らす必要があります。 問題が永続的である場合は、フロントエンドプールのスケールを選択することもできます。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>Skype for Business サーバー自体でこのツールを実行することはできますか?

この操作は必要ありません。 このシナリオは、バイナリの不一致が原因で失敗する可能性があります。また、目標がサーバー上のリソース消費量を測定するためであるため、サポートされていません。 実際にツールを実行していると、サーバーのパフォーマンスに影響し、データと測定値が無効になることがあります。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバーまたは Microsoft Hyper-v Server 2008/2012 で LyncPerfTool を実行できますか?

はいできますよ。
  
## <a name="what-does-mpop-mean"></a>MPOP は何を意味していますか?

MPOP は、"複数のポイントを持つ" と言う短い方法です。 MPOP は、ユーザーが複数のコンピューターまたはデバイスから Skype for Business 2015 クライアントにログオンしているシナリオをシミュレートすることを目的としています。 LyncPerfTool では、各エンドポイントで既定のプロファイルが使用されることに注意してください。 つまり、プロファイルが2つのプレゼンス間で分割されることはありません。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>LyncPerfTool を開始しましたが、何も起こりません。 どうなっているのですか。

サーバー上のアクティブなエンドポイントの合計カウンターを確認して、ユーザーが接続しているかどうかを確認します。 ユーザーが接続していない場合は、Skype for Business Server 2015 の構成を確認してください。 通常発生する問題は、サーバー名、ユーザーのプレフィックス、またはパスワードが間違っていることが原因です。 外部クライアントでは、アクセスプロキシと TargetServer の値を指定する必要があることに注意してください。 構成ファイルでポート番号を確認します。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>何らかの測定が行われているかどうかを確認する方法を教えてください。

ユーザーが接続して操作を実行しているかどうかを示す LyncPerfTool のパフォーマンスカウンターはありますが、操作が測定されているかどうかを確認するには、Skype for Business 2015 クライアントを使用しているアカウントにログオンして実行する方法が最も簡単です。操作を自分で行うことができます。 結果を確認して、測定値が取得されたことを確認します。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 キャパシティプランニングツールと Lync Server 2013 キャパシティプランニングツールがインストールされています。 どうしたらいいですか?

 これらのツールには相互運用性の問題があります。 Skype for Business Server 2015 のストレスとパフォーマンスのツールから有効なデータを取得するには、これらのツールの以前のバージョンをすべてアンインストールする必要があります。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>ストレスとパフォーマンスのツールで CAA を Call Information server topology をセットアップしますか?

いいえ、ツールでは実行されません。 このツールでは、ユーザー、連絡先、配布リストのみを作成して、ユーザーロードをシミュレートできます。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールでサポートされるユーザーの最大数は何人ですか?

テストでは、最大8万ユーザーを作成し、これらのツールを実行する合計3万ユーザーを実行しました。 最大で12万のユーザーを対象としていますが、技術的な制限により高い値を使用できます。 これらの値は、環境内のサーバーとハードウェアに依存していることに注意してください。
  

