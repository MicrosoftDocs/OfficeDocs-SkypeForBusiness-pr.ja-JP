---
title: Skype for Business Server 2015 Stress and Performance Tool の FAQ
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: Skype for Business 2015 Stress and Performance Tool についてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、Stress and Performance ツールの実行中に発生する可能性がある動作の明確化に役立ちます。
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814967"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool の FAQ
 
Skype for Business 2015 Stress and Performance Tool についてよく寄せられる質問 (FAQ)、サポートされているツール構成の確認、ツールの問題のトラブルシューティング、Stress and Performance ツールの実行中に発生する可能性がある動作の明確化に役立ちます。
  
 この FAQ では、Skype for Business Server 2015 Stress and Performance ツールに関してよく寄せられる質問について説明し、トラブルシューティングやツール構成の選択に役立つ場合があります。
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a>実稼働環境でLyncPerfTool.exe実行できますか。

これはお **勧め** しません。 このツールは、実稼働サーバーのパフォーマンス、セキュリティ、およびエンド ユーザー エクスペリエンスに影響します。
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a>ユーザーを初めてログオンします。 サーバーで高負荷が実行されている理由

ユーザーが初めてログオンすると、バックグラウンドで追加の操作が行われます。 その結果、バック エンド サーバー Microsoft SQL Serverパフォーマンスが低下する可能性があります。 すべてのユーザーにログオンする短いテストを実行してから、ツールで結果の測定を開始する前にクライアントを再起動してください。 Skype for Business Server は、1 秒あたり 12 を超える同時ユーザー ログオン セッションをサポートしませんが、サーバーで処理できる実際の数はハードウェア構成によって異なり、サポートされる値よりも小さい場合があります。
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a>クライアントのメモリが使い切っています。 どうすればよいですか?

クライアントのメモリが使い切っている場合は、Skype for Business Server フロント エンド プールごとにログオンしているユーザーの数を減らす必要があります。 問題が解決しない場合は、フロントエンド プールをスケール アウトする方法も選択できます。
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a>このツールを Skype for Business サーバー上で実行できますか。

この操作は行わない方が良い。 このシナリオは、バイナリの不一致が原因で失敗する可能性があります。また、サーバー上のリソース消費を測定する目的のため、サポートされていません。 実際にツールを実行すると、サーバーのパフォーマンスに影響を与え、データと測定値が無効になります。
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a>仮想サーバー上LyncPerfTool.exe Microsoft Hyper-V Server 2008/2012で実行できますか。

はいできますよ。
  
## <a name="what-does-mpop-mean"></a>MPOP の意味

MPOP は、"複数のプレゼンス ポイント" を示す短縮された方法です。 MPOP は、ユーザーが複数のコンピューターまたはデバイスから Skype for Business 2015 クライアントにログオンするシナリオをシミュレートすることを意図しています。 この場合、各エンドポイントLyncPerfTool.exe既定のプロファイルが使用されます。 つまり、プロファイルは 2 つのプレゼンス ポイント間で分割されるのではないのです。
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a>私はLyncPerfTool.exe開始しましたが、何も起こっていません。 何が起こっているのでしょうか?

ユーザーが接続している場合は、サーバーの [アクティブなエンドポイントの合計] カウンターを確認します。 ユーザーが接続していない場合は、Skype for Business Server 2015 の構成を確認します。 通常、表示される問題は、サーバー名、ユーザー プレフィックス、またはパスワードの 1 つが正しくないので発生します。 外部クライアントでは、アクセス プロキシと TargetServer の値を指定する必要があります。 構成ファイルのポート番号を確認します。
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a>何かが測定されているのを確認する方法

LyncPerfTool パフォーマンス カウンターは、ユーザーが接続してアクションを実行するかどうかを示しますが、アクションが測定されているかどうかを確認する最も簡単な方法は、Skype for Business 2015 クライアントを使用してアカウントの 1 つにログオンし、それらのアクションを自分で実行する方法です。 結果を確認して測定値が取られたか確認します。
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a>Lync Server 2010 Capacity Planning Tools または Lync Server 2013 Capacity Planning ツールがインストールされています。 問題ありませんか?

 これらのツールには相互運用性の問題があります。 Skype for Business Server 2015 Stress and Performance ツールから有効なデータを取得するには、これらのツールのすべての以前のバージョンをアンインストールする必要があります。
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a>Stress and Performance ツールは CAA 通話情報サーバー トポロジをセットアップしますか?

いいえ、ツールではこれを行う必要はありません。 ツールは、ユーザー負荷をシミュレートするために、ユーザー、連絡先、および配布リストのみを作成します。
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a>ツールがサポートするユーザーの最大数は何ですか?

テストでは、最大 80,000 ユーザーを作成し、これらのツールを実行する合計 30,000 ユーザーのテストを実行しました。 最大 120,000 ユーザーをお勧めしますが、技術的な制限により高い値が可能です。 これらの値は環境内のサーバーとハードウェアに依存します。
  

