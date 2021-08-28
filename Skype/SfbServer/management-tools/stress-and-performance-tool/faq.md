---
title: 2015 年Skype for Business Serverパフォーマンス ツールに関する FAQ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 ストレスとパフォーマンス ツールのよく寄せられる質問 (FAQ) は、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスとパフォーマンス ツールの実行時に表示される動作の明確化に役立ちます。
ms.openlocfilehash: 42fdf53965e190e98e716df0780eac04565d0767
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611936"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>2015 年Skype for Business Serverパフォーマンス ツールに関する FAQ
 
Skype for Business 2015 ストレスとパフォーマンス ツールのよく寄せられる質問 (FAQ) は、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、ストレスとパフォーマンス ツールの実行時に表示される動作の明確化に役立ちます。
  
 この FAQ では、Skype for Business Server 2015 ストレスとパフォーマンス ツールに関してよく寄せられる質問の一部について説明します。トラブルシューティングとツール構成の選択に役立つ場合があります。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>実稼働環境でLyncPerfTool.exe実行できますか?

これはお **勧め** しません。 このツールは、実稼働サーバーのパフォーマンス、セキュリティ、エンド ユーザー エクスペリエンスに影響を与えます。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>ユーザーを初めてログオンします。 サーバーが高負荷を実行している理由

ユーザーが初めてログオンすると、バックグラウンドで追加の操作が行われます。 その結果、バック エンド サーバーのパフォーマンスMicrosoft SQL Server低下する可能性があります。 ツールで結果の測定を開始する前に、すべてのユーザーにログオンし、クライアントを再起動する短いテストを実行してください。 Skype for Business Serverは、1 秒あたり 12 を超える同時ユーザー ログオン セッションをサポートしませんが、サーバーで処理できる実際の数はハードウェア構成によって異なり、サポートされている値よりも小さい場合があります。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントがメモリを使い切っています。 どうすればよいですか?

クライアントがメモリを使い切っている場合は、フロントエンド プールごとにログオンしているユーザー Skype for Business Server減らす必要があります。 問題が永続的な場合は、フロントエンド プールをスケール アウトする方法も選択できます。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>このツールは、サーバー自体Skype for Business実行できますか?

この操作は行う必要があります。 このシナリオは、バイナリの不一致が原因で失敗する可能性がある場合や、サーバー上のリソース消費量を測定する目的のため、サポートされていません。 実際にツールを実行すると、サーバーのパフォーマンスに影響を与え、データと測定値が無効になります。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバーまたは LyncPerfTool.exeサーバー 2008/2012 でMicrosoft Hyper-Vを実行できますか?

はいできますよ。
  
## <a name="what-does-mpop-mean"></a>MPOP とはどういう意味ですか?

MPOP は、"複数のプレゼンス ポイント" という短い方法です。 MPOP は、ユーザーが複数のコンピューターまたはデバイスから 2015 Skype for Businessクライアントにログオンするシナリオをシミュレートすることを意図しています。 この場合、各エンドポイントLyncPerfTool.exe既定のプロファイルが使用されます。 つまり、プロファイルは 2 つのプレゼンス ポイント間で分割されるのではないのです。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>私はLyncPerfTool.exe始めましたが、何も起こっていません。 何が起こっているのでしょうか?

サーバーの [アクティブなエンドポイントの合計] カウンターを確認して、ユーザーが接続している場合を確認します。 ユーザーが接続していない場合は、2015 Skype for Business Serverを確認します。 通常、表示される問題は、サーバー名、ユーザー プレフィックス、またはパスワードの 1 つが正しくないので発生します。 外部クライアントは、Access Proxy と TargetServer の値を指定する必要があります。 構成ファイルのポート番号を確認します。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>何かが測定されているのを確認するには、どうすれば良いですか?

LyncPerfTool のパフォーマンス カウンターは、ユーザーがアクションを接続して実行するかどうかを示しますが、アクションが測定されているかどうかを確認する最も簡単な方法は、Skype for Business 2015 クライアントを使用してアカウントの 1 つにログオンし、それらのアクションを自分で実行する方法です。 結果を確認して、測定値が取られたか確認します。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 容量計画ツールまたは Lync Server 2013 容量計画ツールがインストールされています。 大丈夫ですか?

 これらのツールには相互運用性の問題があります。 2015 年のストレスとパフォーマンス ツールから有効なデータを取得するには、これらのツールの以前Skype for Business Serverアンインストールする必要があります。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>ストレスとパフォーマンス ツールは CAA 通話情報サーバー トポロジをセットアップしますか?

いいえ、ツールはこれを行う必要はありません。 ツールは、ユーザーの負荷をシミュレートするために、ユーザー、連絡先、配布リストのみを作成します。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールがサポートするユーザーの最大数は何ですか?

テストでは、最大 80,000 人のユーザーが作成され、これらのツールを実行している合計 30,000 人のユーザーがテストを実行しました。 技術的な制限により高い値が可能ですが、最大 120,000 人のユーザーを推奨します。 これらの値は、環境内のサーバーとハードウェアによって異なります。
  

