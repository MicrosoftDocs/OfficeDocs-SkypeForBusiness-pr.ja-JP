---
title: 'Lync Server 2013: リバース プロキシ サーバーの DNS レコードの作成'
TOCTitle: リバース プロキシ サーバーの DNS レコードの作成
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48273326
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのリバース プロキシ サーバーの DNS レコードの作成

 

_**トピックの最終更新日:** 2013-03-29_

「[Lync Server 2013 でのエッジ サポートの DNS の構成](lync-server-2013-configure-dns-for-edge-support.md)」の説明に従って、Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1、Forefront Threat Management Gateway 2010 Server または Internet Information Server アプリケーション要求ルーティング処理のパブリック外部インターフェイスを指す外部 DNS A レコードを作成します。プール、ディレクター (または ディレクター プール)、簡易 URL ごとに、外部 Web サービス FQDN の DNS レコードが必要です。

リバース プロキシへのクライアント解決用の最小 DNS レコードとして、次のレコードを作成する必要があります。

  - ディレクターおよび ディレクター プールの公開外部 Web サービスを定義するホスト (A) レコード (例: **webdirext.contoso.com** )

  - 任意の フロント エンド プールおよび Standard Edition サーバーの役割にホストされる外部 Web サービスの公開外部 Web サービスを定義するホスト (A) レコード (例: **webext.contoso.com** )

  - 簡易 URL のホスト (A) レコード (例: **dialin.contoso.com** および **meet.contoso.com** )

  - Lync Discover External レコードのホスト (A) レコード。 Lync Web App、スケジューラ、モビリティなどのすべての Web アプリケーションに対して AutoDiscover へのポインターも提供します (例: **lyncdiscover.contoso.com** )

  - Office Web Apps サーバー URL のホスト (A) レコード (例: **officewebapp01.contoso.com**)

詳細については、「[DNS の概要 - Lync Server 2013 でのリバース プロキシ](lync-server-2013-dns-summary-reverse-proxy.md)」を参照してください。

