---
title: 移行のためのクライアントの構成
TOCTitle: 移行のためのクライアントの構成
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49887047
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 移行のためのクライアントの構成

 

_**トピックの最終更新日:** 2016-12-08_

このトピックでは、 Lync Server 2013 へ移行する前に遂行すべき推奨クライアント展開手順を説明します。これらの構成変更は、 Office Communications Server 2007 R2 で行ってください。これらの手順を移行前に遂行することが何よりも重要です。詳しくは、「 [Lync Server 2013 のクライアントとデバイスの計画](lync-server-2013-planning-for-clients-and-devices.md)」をご覧ください。

## 移行の前にクライアントを構成するには

1.  最新の Office Communications Server 2007 R2 サーバー、クライアント、デバイス更新プログラム (修正プログラム) を展開します。
    
      - [Office Communications Server 2007 R2 更新プログラムの適用](apply-office-communications-server-2007-r2-updates.md)
    
      - [Communicator 2007 R2 の累積的な更新プログラム パッケージの説明](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [デバイスのソフトウェア アップデートの入手 (Obtaining Software Updates for Devices)](http://go.microsoft.com/fwlink/?linkid=335809)

2.  Office Communications Server 2007 R2 で、クライアント バージョン フィルターを使用して最新の更新プログラムがインストールされた Office Communications Server 2007 R2 クライアントのみにサインインを許可します。

3.  Office Communications Server 2007 R2 で、クライアント バージョン フィルターを使用して、 Lync Server 2013 クライアントがサインインできないようにします。「**クライアント バージョン フィルターの構成 (英語)**」([http://go.microsoft.com/fwlink/?linkid=202488\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202488%26clcid=0x411)) の手順に従って、次の表に記されているバージョン フィルターを追加します。各バージョン フィルターで、\[ **ブロック** \] のアクションを割り当てます。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>クライアント</th>
    <th>ユーザー エージェントのヘッダー</th>
    <th>バージョン</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*.*</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*.*</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*.*</p></td>
    </tr>
    </tbody>
    </table>

