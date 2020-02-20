---
title: 'Lync Server 2013: ディレクターのハードウェアおよびソフトウェア要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff5e28b21e06cc438c7eb092515443579f5c004
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155029"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

このセクションでは、ディレクターのハードウェアおよびソフトウェア要件と、ディレクターがサポートする併置シナリオについて詳しく説明します。

<div>

## <a name="hardware-requirements-for-the-director"></a>ディレクターのハードウェア要件

次の表に、ディレクターのハードウェア要件を示します。

### <a name="hardware-requirements-for-the-director"></a>ディレクターのハードウェア要件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ハードウェア コンポーネント</th>
<th>最小要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>2.0 GHz またはそれ以上の 64 ビット プロセッサ、クアッド コア</p></li>
<li><p>2.0 GHz またはそれ以上の 64 ビット デュアル プロセッサ、デュアル コア</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>4 ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10K RPM ハード ディスク ドライブ (HDD)</p></li>
<li><p>10K RPM HDD 以上のパフォーマンスを持つハイパフォーマンス ソリッド ステート ドライブ (SSD)</p></li>
<li><p>データベース データ ファイル用として 2 x RAID 10 (ストライプおよびミラー)、15K RPM ディスク</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>1 Gbps (ギガビット/秒) のデュアル ネットワーク アダプター (推奨)</p></li>
<li><p>1 Gbps の単一ネットワーク アダプター (サポート)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>ディレクターのソフトウェア要件

ディレクターの役割は、Lync Server 2013 Enterprise Edition を実行しているサーバーにのみ展開できます。

ディレクターには、次のいずれかの64ビットオペレーティングシステムが必要です。

  - Windows Server 2008 R2 Standard オペレーティングシステム Service Pack 1

  - Windows Server 2008 R2 Enterprise オペレーティングシステム Service Pack 1

  - Windows Server 2008 R2 Datacenter オペレーティングシステムと Service Pack 1

  - Windows Server 2012 Standard オペレーティングシステム

  - Windows Server 2012 Datacenter オペレーティングシステム

Lync Server 2013 では、「 [Lync server 2013 の追加サーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」で説明されている次のプログラムと更新プログラムのインストールも必要です。

</div>

<div>

## <a name="supported-collocation"></a>サポートされる配置

ディレクターサーバーの役割を、Lync Server 2013 の他のサーバーの役割と併置することはできません。 ただし、ディレクターを展開しない場合は、フロントエンドサーバーによって役割が引き受けられます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

