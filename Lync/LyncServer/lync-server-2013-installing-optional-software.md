---
title: 'Lync Server 2013: オプションのソフトウェアをインストールする'
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
ms.openlocfilehash: a493fed33fff897ea2cccc2a89c0d55c5b8a8097
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Lync Server 2013 でオプションのソフトウェアをインストールする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

Microsoft Lync Server 2013 の計画ツールは、Microsoft Excel と Microsoft Visio にエクスポートするように設計されています。 これらのアプリケーションは計画ツールの操作には必要ありませんが、設計の展開とドキュメントに大きな価値を加えることになります。

<div>

## <a name="optional-software"></a>オプション ソフトウェア

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

デザインを Microsoft Excel にエクスポートすると、次の 7 つのタブがあるスプレッドシートを表示するレポートが作成されます。

  - 概要 - ユーザー数、容量の設定値、サーバー プロファイル情報などの、サイトの構成情報を表示します。

  - ハードウェアのプロファイル - CPU、メモリ、ディスク、ネットワーク インターフェイスなど、トポロジで指定されているサーバーの推奨ハードウェア構成についてのレポートを表示します。サーバー コンポーネントの数量および推奨仕様も含まれます。各サーバーはサイト別に定義されているので、サイトごとのサーバー要件を詳細に示します。

  - ポートの要件 - 有効にされているすべてのポートのレポートと、DNS 負荷分散 (DNS LB) およびロード バランサー機器 (HLB) への関連付けのレポートを表示します。このレポートは、ファイアウォール、DNS LB、および HLB の構成を計画するために使用します。

  - 概要レポート–エッジサーバーネットワークのセットアップに必要な設定の一般的な概要が表示されます。

  - 証明書レポート–エッジサーバーを実行するために必要な証明書に必要なサブジェクト名とサブジェクトの代替名が表示されます。

  - ファイアウォール レポート - 内部および外部インターフェイス用の発信元および宛先のポートと IP アドレスを表示します。

  - DNS レポート - 作成する DNS エントリごとに必要な完全修飾ドメイン名 (FQDN) と IP/VIP アドレスを表示します。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

設計を Microsoft Visio にエクスポートすると、構成されたトポロジおよびインフラストラクチャのドキュメントに使用できるダイアグラムが作成されます。インポートされたダイアグラムは、ドキュメントのニーズに合わせて編集や再編成ができます。一般的な Visio のダイアグラムには、次の要素が含まれます。

<div>


> [!NOTE]  
> 3台以上のフロントエンドサーバーが必要な設計の場合は、フロントエンドプール、フロントエンドサーバー、SQL Server を実行しているコンピューター、IP アドレス、Fqdn の追加ページが作成されます。



</div>

  - グローバルトポロジ–構成済みの Lync Server 2013 サイトの図。

  - [サイト名] タブ– Edge Server、ファイアウォール、公衆交換電話網 (PSTN)、および内部サーバーの展開を使用して、サイトの構成トポロジを表示します。 内部展開は、フロントエンドプール、SQL Server ベースのサーバー、Active Directory ドメインサービス、ディレクター、Exchange ユニファイドメッセージング (UM) サーバー、Exchange メールボックスサーバー、Office Web Apps サーバーなど、構成済みのサーバーとプールで構成されます。仲介サーバーと常設チャットサーバー。

  - エッジネットワーク図–関連する IP アドレスと Fqdn を含むエッジサーバー構成の詳細な図。 DNS 負荷分散やロード バランサー機器も含まれます。 さらに、関連付けられた DNS LB または HLB および割り当てられた IP アドレス (計画ツールが IPv4 アドレスと IPv6 アドレスの両方をサポートします) と FQDN が表示されたディレクターとフロントエンドサーバーまたはフロントエンドプールが表示されます。

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

