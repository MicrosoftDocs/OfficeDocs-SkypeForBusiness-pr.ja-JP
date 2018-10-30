---
title: Lync Server 2013 の証明書インフラストラクチャの要件
TOCTitle: 証明書インフラストラクチャの要件
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48271052
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の証明書インフラストラクチャの要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、TLS 接続および相互 TLS (MTLS) 接続をサポートするための公開キー基盤 (PKI) が必要です。

Lync Server は、以下の目的で証明書を使用します。

  - クライアントとサーバー間の TLS 接続

  - サーバー間の MTLS 接続

  - パートナーの自動 DNS 検出を使用するフェデレーション

  - インスタント メッセージング (IM) 用のリモート ユーザー アクセス

  - 音声/ビデオ (A/V) セッション、アプリケーション共有、および会議への外部ユーザー アクセス

  - Web サービスの自動検出を使用するモバイル要求

Lync Server の場合、以下の一般的な要件が適用されます。

  - すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。

  - すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。

  - すべての証明書が、オペレーティング システムでサポートされている署名アルゴリズムによって署名されている必要がある。 Lync Server 2013 は SHA-1 と SHA-2 のダイジェスト サイズ (224、256、384、512 ビット) をサポートしており、オペレーティング システムの要件を満たすか、それを上回ります。オペレーティング システム サポートについては、[http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002) を参照してください。

  - Lync Server を実行している内部サーバーでは、自動登録がサポートされている。

  - Lync Server エッジ サーバーでは、自動登録がサポートされていない。

  - Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。
    
    KB922706 は、Windows Server 2003 証明書サービスの Web 登録について Web 証明書の登録に関わる問題解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して、Windows Server 2003 CA から証明書を要求できるようにはなりません。

  - 暗証キーの長さとして 1024、2048、4096 がサポートされます。2048 以上のキーの長さはお勧めしません。

  - 既定のダイジェストまたはハッシュ アルゴリズムは RSA です。ECDH\_P256、ECDH\_P384、ECDH\_P521 のハッシュ アルゴリズムもサポートされます。

## このセクション中

  - [Lync Server 2013 の内部サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 の常設チャット サーバーに対する証明書要件](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 のモビリティの証明書の要件](lync-server-2013-certificate-requirements-for-mobility.md)

