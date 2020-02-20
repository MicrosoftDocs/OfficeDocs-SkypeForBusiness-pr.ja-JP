---
title: 'Lync Server 2013: オプションのソフトウェアのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5eaee8ba62984ad37dc49df2ce609018dd17b79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Lync Server 2013 でオプションのソフトウェアをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Microsoft Lync Server 2013、計画ツールは、Microsoft Excel および Microsoft Visio にエクスポートするように設計されています。 これらのアプリケーションは、計画ツールの操作に必要ではありませんが、設計の展開とドキュメントに大きな価値が追加されています。

<div>

## <a name="optional-software"></a>オプション ソフトウェア

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

デザインを Microsoft Excel にエクスポートすると、スプレッドシートに7つのタブを表示するレポートが作成されます。

  - 概要-ユーザー数、容量の設定、サーバープロファイル情報など、サイトの構成に関する情報を表示します。

  - ハードウェアのプロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成についてのレポートを表示します。 サーバーコンポーネントの数量および推奨仕様も含まれています。 さらに、各サーバーはサイトごとに定義されており、サイトごとにサーバーの要件を完全に表現します。

  - [ポートの要件] –有効になっているすべてのポートのレポートと、ドメインネームシステムの負荷分散 (DNS LB) およびハードウェアロードバランサー (HLB) への関連付けが表示されます。 このレポートを使用して、ファイアウォールと DNS LB および HLB の構成を計画する必要があります。

  - [概要レポート]: エッジサーバーネットワークの設定に必要な設定の概要を表示します。

  - 証明書レポート-エッジサーバーを実行するのに必要な証明書に必要なサブジェクト名とサブジェクトの別名が表示されます。

  - ファイアウォールレポート-外部および内部インターフェイスの送信元と宛先のポートと IP アドレスが表示されます。

  - DNS レポート-作成する各 DNS エントリに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスが表示されます。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。

<div>


> [!NOTE]  
> 3台以上のフロントエンドサーバーを必要とする程度のサイズの設計では、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、および Fqdn に対して追加のページが作成されます。



</div>

  - グローバルトポロジ–構成された Lync Server 2013 サイトの図。

  - [サイト名] タブ–エッジサーバー、ファイアウォール、公衆交換電話網 (PSTN) とゲートウェイを使用したサイト構成トポロジ、および内部サーバー展開が表示されます。 内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバー、などの構成済みのサーバーとプールで構成されます。仲介サーバー、および常設チャットサーバー。

  - エッジネットワーク図–関連する IP アドレスと Fqdn を使用したエッジサーバー構成の詳細な図。 DNS 負荷分散とロードバランサー機器も含まれています。 さらに、ディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。これには、関連付けられた DNS LB または HLB と、割り当てられた IP アドレス (計画ツールは、IPv4 と IPv6 の両方のアドレスをサポートします) と FQDN が表示されます。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での計画ツールのインストール](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

