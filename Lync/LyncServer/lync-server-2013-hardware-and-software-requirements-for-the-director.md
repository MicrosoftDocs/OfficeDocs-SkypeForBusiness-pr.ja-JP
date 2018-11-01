---
title: 'Lync Server 2013: ディレクターのハードウェアおよびソフトウェア要件'
TOCTitle: ディレクターのハードウェアおよびソフトウェア要件
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48272527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のディレクターのハードウェアおよびソフトウェア要件

 

_**トピックの最終更新日:** 2016-05-19_

このセクションでは、ディレクターのハードウェアおよびソフトウェア要件と、ディレクターでサポートされる併置シナリオについて説明します。

## ディレクターのハードウェア要件

次の表に、ディレクターのハードウェア要件を示します。

### ディレクターのハードウェア要件

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


## ディレクターのソフトウェア要件

ディレクターの役割は、Lync Server 2013 Enterprise Edition を実行しているサーバーにのみ展開できます。

ディレクターでは、次のいずれかの 64 ビット オペレーティング システムが必要です。

  - Windows Server 2008 R2 Standard オペレーティング システム Service Pack 1

  - Windows Server 2008 R2 Enterprise オペレーティング システム Service Pack 1

  - Windows Server 2008 R2 Datacenter オペレーティング システム Service Pack 1

  - Windows Server 2012 Standard オペレーティング システム

  - Windows Server 2012 Datacenter オペレーティング システム

Lync Server 2013 では、次のプログラムと更新プログラムもインストールする必要があります。詳細については、「[Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。

## サポートされる併置

ディレクター サーバーの役割は、Lync Server 2013 内の他のどんなサーバーの役割とも併置できません。ただし、ディレクターを展開しない場合は、フロント エンド サーバーがその役割を引き受けることになります。

