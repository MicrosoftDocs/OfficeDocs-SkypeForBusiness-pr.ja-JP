---
title: ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype ビジネス 2015年のストレスおよびパフォーマンス ツールについてよく寄せられる質問 (FAQ)、どのようなツールの構成がサポートされているを検索、ツールに関する問題のトラブルシューティング、およびストレスおよびパフォーマンス ツールを実行するときに表示される動作を明確にすることに便利です。.
ms.openlocfilehash: 730f9620e4aa498df26cc24f3c17ea1bd2ad7d5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>ビジネス 2015 のサーバの負荷とパフォーマンス ツールの Skype のよく寄せられる質問
 
Skype ビジネス 2015年のストレスおよびパフォーマンス ツールについてよく寄せられる質問 (FAQ)、どのようなツールの構成がサポートされているを検索、ツールに関する問題のトラブルシューティング、およびストレスおよびパフォーマンス ツールを実行するときに表示される動作を明確にすることに便利です。.
  
 この FAQ では、ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールでは、Skype に関してよく寄せられる質問について説明し、トラブルシューティングおよびツールの構成の選択に役立つことがあります。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>実稼働環境で LyncPerfTool.exe を実行することができますか。

これはお勧め**できません**。 ツール、本番サーバのパフォーマンス、セキュリティ、およびエンド ユーザー エクスペリエンスに影響します。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>ログオン ユーザーを最初にします。 高負荷サーバー実行しているでしょうか。

初めてユーザーがログオンすると、追加の操作は、バック グラウンドで行われます。 結果として、Microsoft SQL Server バック エンド サーバーにパフォーマンスが低下することができます。 ユーザーのすべてのログに記録する簡単なテストを実行し、ツールを使用して結果を測定を開始する前にクライアントを再起動し、実行することをお勧めします。 Skype ビジネス サーバーは、1 秒あたり 12 個を超えるの同時ユーザー ログオン セッションをサポートしないですが、サーバーで処理できる実際の数は、ハードウェアの構成によって異なり、サポートされている値よりも小さい場合があります注意してください。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントでメモリが不足しています! どうしたらいいでしょう。

クライアントがメモリから実行している場合は、ビジネス サーバーのフロント エンド プールの Skype あたりログオンしたユーザーの数を減らす必要があります。 問題が永続的な場合は、最後のプール拡張正面にもできます。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>に対して実行できますこのツール ビジネスのサーバーで、Skype 自体ですか。

するべきではありません。 バイナリが一致しないのため、エラーが表示するために、このシナリオがサポートされていないと、目標は、サーバー上のリソースの消費量を測定するためです。 実際には、ツールの実行が、サーバーのパフォーマンスに影響を与えるデータと測定値が無効になります。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバー上または [Microsoft HYPER-V Server 2008/2012 に LyncPerfTool.exe を実行することができますか。

はいできますよ。
  
## <a name="what-does-mpop-mean"></a>MPOP は何を意味しますか。

MPOP は、「プレゼンスの複数のポイント」言い換えると簡略化された方法です。 MPOP は、ユーザーがログオンしている Skype をビジネス 2015年クライアントの複数のコンピューターまたはデバイスからのシナリオをシミュレートするものです。 、LyncPerfTool.exe、の各エンドポイントを使用する既定のプロファイルに注意します。 つまり、プロファイルは、プレゼンスの 2 つの点の間で分割されていません。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>LyncPerfTool.exe を起動しましたが、何も起こらない。 どうなっているのですか。

ユーザーが接続しているかどうかを参照してくださいサーバーのアクティブなエンドポイントの合計カウンターを確認してください。 ユーザーが接続していない場合、Skype をビジネス サーバー 2015 の構成を確認します。 皆さんは通常この問題は、サーバー名、ユーザーのプレフィックス、またはパスワードのいずれかが間違っているために発生します。 外部クライアントがアクセス プロキシと対象サーバーの値を指定する必要があります注意してをください。 構成ファイル内のポート番号を確認します。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>何かが計測されることを確認する方法は?

ユーザーが接続しているかどうかと、実行するアクションを示すパフォーマンス カウンターは LyncPerfTool ですが、アクションが測定されているかどうかを確認する最も簡単な方法は、Skype ビジネス 2015年クライアント用のアカウントのいずれかにログオンし、これらの操作を行いますアクション自分でします。 測定値を確認するのには結果が取得されたかを確認します。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 の容量計画ツールと Lync Server 2013 の容量計画ツールのインストールがあるとします。 いいですか。

 これらのツールには、相互運用性の問題があります。 ビジネス サーバー 2015 応力の Skype から有効なデータを取得するのにはこれらのツールとパフォーマンス ツールの以前のバージョンをすべてアンインストールする必要があります。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>ストレスおよびパフォーマンス ツールが CAA 呼び出し情報のサーバー トポロジを設定するのでしょうか。

残念ですが、ツールは、このことはありません。 ツールは、ユーザー、連絡先、および配布リスト、ユーザーの負荷をシミュレートするためにのみ作成します。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールがサポートできるユーザーの最大数とは何ですか。

テストでは、私たち最大 80,000 ユーザーの作成して合計 30,000 人のユーザーがこれらのツールを実行するテストを実行します。 最大 120,000 のユーザーは、技術的な制限の値を大きくできますが、お勧めします。 これらの値は、サーバーと、環境内のハードウェアに依存していることを忘れないでください。
  

