---
title: Lync Server 2013 のワイルドカード証明書のサポート
TOCTitle: ワイルドカード証明書のサポート
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48271225
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のワイルドカード証明書のサポート

 

_**トピックの最終更新日:** 2013-03-21_

Lync Server 2013 では、通信の暗号化とサーバーの ID 認証に証明書を使用します。リーバース プロキシ経由の Web 公開など、状況によっては、サービスを提供するサーバーの完全修飾ドメイン名 (FQDN) と一致する厳密なサブジェクトの別名 (SAN) エントリが不要な場合もあります。そのような場合には、ワイルドカード SAN エントリが含まれる証明書 (一般に "ワイルドカード証明書" といいます) を使用でき、それによって、公的証明機関から請求される証明書コストを削減し、証明書の計画プロセスの複雑さを緩和できます。


> [!WARNING]
> 統合コミュニケーション (UC) デバイス (電話など) の機能を保持するには、展開された証明書を十分にテストして、ワイルカード証明書を実装した後もデバイスが正しく動作することを確認してください。



サブジェクト名 (共通名 (CN) ともいいます) としてのワイルドカード エントリは、どの役割でもサポートされません。SAN のワイルドカード エントリ使用は、次のサーバーの役割でサポートされます。

  - **リバース プロキシ。**   ワイルドカード SAN エントリは、簡易 URL (会議とダイヤルイン) 発行元証明書でサポートされます。

  - **リバース プロキシ。**   ワイルドカード SAN エントリは、発行元証明書の LyncDiscover の SAN エントリでサポートされます。

  - **ディレクター。**   ワイルドカード SAN エントリは、簡易 URL (会議とダイヤルイン) と、ディレクターの Web コンポーネントの LyncDiscover および LyncDiscoverInternal の SAN エントリでサポートされます。

  - **フロント エンド サーバー (Standard Edition) および フロント エンド プール (Enterprise Edition)。** ワイルドカード SAN エントリは、簡易 URL (会議とダイヤルイン) と、フロントエンドの Web コンポーネントの LyncDiscover および LyncDiscoverInternal の SAN エントリでサポートされます。

  - **Exchange ユニファイド メッセージング (UM)。**   スタンドアロン サーバーとして展開されたサーバーは、SAN エントリを使用しません。

  - **Microsoft Exchange Server クライアント アクセス サーバー。**   SAN のワイルドカード エントリは、内部と外部のクライアントでサポートされます。

  - **同じサーバー上の Exchange ユニファイド メッセージング (UM) および Microsoft Exchange Server クライアント アクセス サーバー。**   ワイルドカード SAN エントリがサポートされます。

次のサーバーの役割は、このトピックの対象外です。

  - 内部サーバーの役割 (仲介サーバー、アーカイブおよび監視サーバー、存続可能ブランチ アプライアンス、存続可能ブランチ サーバーが含まれますが、これらに限定されません)

  - 外部 エッジ サーバー インターフェイス

  - 内部 エッジ サーバー
    
    > [!NOTE]
    > 内部 エッジ サーバー インターフェイスでは、ワイルドカード エントリは SAN に割り当て可能で、サポートされています。内部 エッジ サーバーでは SAN は照会されず、ワイルドカード SAN エントリの効果は限られています。


証明書でのワイルドカードの使用方法についてなど、証明書の構成の詳細については、次のトピックを参照してください。

  - [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [証明書の概要 - Lync Server 2013 の DNS および HLB による負荷分散](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [証明書の概要 - Lync Server 2013 の単一ディレクター](lync-server-2013-certificate-summary-single-director.md)

  - [証明書の概要 - Lync Server 2013 の拡張ディレクター プール、ハードウェア ロード バランサー](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [証明書の概要 - Lync Server 2013 リバース プロキシ](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

ワイルドカードの使用方法についてなど、Exchange 用の証明書の構成の詳細については、Exchange 2013 製品のドキュメントを参照してください。

