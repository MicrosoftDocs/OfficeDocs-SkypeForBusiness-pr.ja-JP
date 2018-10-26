---
title: 'Lync Server 2013: 外部ユーザー アクセス用のファイアウォールとポートの構成'
TOCTitle: 外部ユーザー アクセス用のファイアウォールとポートの構成
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48273603
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での外部ユーザー アクセス用のファイアウォールとポートの構成

 

_**トピックの最終更新日:** 2012-05-21_

ファイアウォールとポートを構成するには、エッジ サーバー、リバース プロキシ サーバー、および場合によってはハードウェア ロード バランサー (DNS 負荷分散を使用しない拡張展開の場合) でそれらの設定を構成する必要があります。ここでは、すべてのエッジ サーバー コンポーネントのファイアウォールとポート要件、およびエッジ サーバーのファイウォール ポートの構成に関する情報を提供します。リバース プロキシ サーバーのポートの構成の詳細については、「[Lync Server 2013 のリバース プロキシ サーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md)」を参照してください。拡張されたエッジ トポロジを展開し、DNS 負荷分散の代わりにハードウェア負荷分散を使用する場合は、ハードウェア ロード バランサーのポートの構成の詳細について、「計画」のドキュメントの「[Lync Server 2013 のハードウェア ロード バランサーによる拡張統合エッジ](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)」を参照してください。

## 関連項目

#### 概念

[Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

