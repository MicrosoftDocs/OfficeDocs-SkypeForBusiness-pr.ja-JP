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
ms.openlocfilehash: 087cfed02e3b28df88508446c57e451f42ef067c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513004"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Lync Server 2013 のコアインフラストラクチャのベストプラクティス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-01-27_

一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらの方法は、Microsoft Lync Server 2013 インフラストラクチャだけでなく、ネットワーク全体にとってもメリットがあります。 これらのプラクティスを実装していない場合は、Lync Server 2013 を展開する前に実行することをお勧めします。

Lync Server 2013 の展開において、ダウンタイムが発生する可能性がある偶発的または意図的の悪影響からサーバーを保護するために、次の対策を講じる必要があります。

  - 各サーバーに、常に最新のセキュリティ更新プログラムを適用します。 マイクロソフト テクニカル セキュリティ情報通知サービスに登録すると、マイクロソフト製品に関するセキュリティ速報を受信できます。 サブスクライブするには、の Microsoft テクニカルセキュリティ通知 web サイトにアクセスして [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) ください。

  - アクセス権が正しく設定されていることを確認します。

  - 物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。

  - Lync Server 2013 をインストールするコンピューターでは必要ない Windows Server オペレーティングシステムサービスを無効にすることをお勧めします。

  - サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。

  - サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。 DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。

</div>

<span> </span>

</div>

</div>

</div>

