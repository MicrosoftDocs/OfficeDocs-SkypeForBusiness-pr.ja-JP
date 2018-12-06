---
title: Lync Online の顧客との通信を確認する
TOCTitle: Lync Online の顧客との通信を確認する
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48273546
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Online の顧客との通信を確認する

 

_**トピックの最終更新日:** 2016-12-08_

組織の Lync ユーザーと Microsoft Lync Online 2010 の顧客のユーザーとの通信を可能にするには、次の手順を完了する必要があります。

  - すべての前提条件を満たします。このための作業には、内部サーバーとエッジ サーバーを展開する、組織に対してフェデレーションのサポートを有効にする、ユーザー アカウントを設定するなどがあります。詳細については、「[Lync Online の顧客とのフェデレーションの前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」を参照してください。

  - 内部展開にドメイン アクセスのサポートを構成します。このための作業には、ホスト プロバイダーのエントリを作成する、Lync Online の顧客のドメインからのアクセスを許可するように展開を構成するなどがあります。詳細については、「[Lync オンライン ドメインのフェデレーション サポートを構成する](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)」を参照してください。

  - フェデレーションをサポートするようにユーザー アカウントを構成します。詳細については、「[Lync Online 顧客によるフェデレーションのユーザー アクセスの構成](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)」を参照してください。

これらの手順がすべて完了し、さらに、Lync Online 2010 の顧客の管理者がオンライン サービスの構成をすべて完了して、組織でフェデレーションをサポートできるようになったら、組織の内部ユーザーと Lync Online の顧客のユーザーの間で通信をテストして、正しく通信できるかどうかを確認します。正しく通信できない場合は、エッジ サーバーからログ ツールを使用し、ログおよびトレース ファイルをキャプチャして問題を解決します。ログ ツールの使用の詳細については、「操作」のドキュメントの「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。ログ ツールの詳細については、TechNet ライブラリの「Lync Server 2010 Logging Tool」([http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265%26clcid=0x411)) を参照してください。

