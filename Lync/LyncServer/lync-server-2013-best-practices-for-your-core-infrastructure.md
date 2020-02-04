---
title: 'Lync Server 2013: コアインフラストラクチャのベストプラクティス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Lync Server 2013 のコアインフラストラクチャのベストプラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-01-27_

システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。 この方法では、Microsoft Lync Server 2013 インフラストラクチャだけでなく、ネットワーク全体も利用できます。 これらのプラクティスを実装していない場合は、Lync Server 2013 を展開する前に、この手順を実行することをお勧めします。

Lync Server 2013 の展開で、ダウンタイムが発生する可能性のある偶発的または明確の危害からサーバーを保護するために、次のことを行う必要があります。

  - 各サーバーに、常に最新のセキュリティ更新プログラムを適用します。 マイクロソフト テクニカル セキュリティ情報通知を購読すると、マイクロソフト製品に関するセキュリティ速報を受信できます。 登録するには、の Microsoft テクニカルセキュリティ通知 web サイト[http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)を参照してください。

  - アクセス権が正しく設定されていることを確認します。

  - 物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。

  - Lync Server 2013 をインストールするコンピューターには必要ない Windows Server オペレーティングシステムサービスを無効にすることをお勧めします。

  - サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。

  - サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。 DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。

</div>

<span> </span>

</div>

</div>

</div>

