---
title: 'Lync Server 2013: リバース プロキシの証明書の設定'
TOCTitle: リバース プロキシの証明書の設定
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48273452
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのリバース プロキシの証明書の設定

 

_**トピックの最終更新日:** 2012-09-08_

各リバース プロキシ サーバーは、リッスン サービスで使用する Web サーバー証明書を必要とします。Web サーバー証明書は、パブリック証明機関 (CA) が発行する必要があります。

この証明書およびその他の証明書の要件の詳細については、「[Lync Server 2013 における外部ユーザー アクセスに対する証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。

## リバース プロキシの Web サービス証明書を設定するには

  - Web サービス証明書の設定を含め、既にリバース プロキシの設定が済んでいる必要があります。エッジ サーバーの展開を開始する前にその設定を行わなかった場合は、「[Lync Server 2013 のリバース プロキシ サーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md)」の手順に従って、要求を作成し、Web サービス証明書をインストールし、各 Web 公開ルールを作成して、証明書を使用するようにルールを構成してください。

