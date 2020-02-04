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
ms.openlocfilehash: 52d91a739935b2e42bb925d5645350c5875e5b43
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

このセクションでは、監督のハードウェアとソフトウェアの要件、およびディレクターのサポートされる collocation シナリオについて説明します。

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
<li><p>64ビットプロセッサ、クアッドコア、2.0 GHz 以上</p></li>
<li><p>64ビットデュアルプロセッサ、デュアルコア、2.0 GHz 以上</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>メモリ</p></td>
<td><p>4ギガバイト (GB)</p></td>
</tr>
<tr class="odd">
<td><p>ディスク</p></td>
<td><ul>
<li><p>10K RPM ハードディスクドライブ (HDD)</p></li>
<li><p>高パフォーマンスのソリッドステートドライブ (SSD) と、10K RPM HDD と同等またはそれ以上のパフォーマンス。</p></li>
<li><p>データベースデータファイル用の2倍の RAID 10 (ストライピングとミラーリング) 15K RPM ディスク</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ネットワーク</p></td>
<td><ul>
<li><p>デュアル1ギガビット/秒 (Gbps) ネットワークアダプター (推奨)</p></li>
<li><p>1つの 1 Gbps ネットワークアダプター (サポートされています)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>ディレクターのソフトウェア要件

ディレクターの役割は、Lync Server 2013 Enterprise Edition を実行しているサーバーにのみ展開できます。

ディレクターには、次のいずれかの64ビットオペレーティングシステムが必要です。

  - Windows Server 2008 R2 Standard オペレーティングシステム (Service Pack 1)

  - Windows Server 2008 R2 Enterprise オペレーティングシステム (Service Pack 1)

  - Windows Server 2008 R2 Datacenter オペレーティングシステムと Service Pack 1

  - Windows Server 2012 標準オペレーティングシステム

  - Windows Server 2012 Datacenter オペレーティングシステム

また、lync Server 2013 には、「 [Lync server 2013 のその他のサーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」で説明されている、次のプログラムと更新プログラムのインストールが必要です。

</div>

<div>

## <a name="supported-collocation"></a>サポートされている Collocation

ディレクターサーバーの役割は、Lync Server 2013 の他のサーバーの役割とは関係ありません。 ただし、ディレクターを展開しない場合は、フロントエンドサーバーによって役割が想定されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

