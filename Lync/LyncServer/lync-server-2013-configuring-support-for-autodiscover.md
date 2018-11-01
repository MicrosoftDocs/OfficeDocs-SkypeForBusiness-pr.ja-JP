---
title: 自動検出のサポートの構成
TOCTitle: 自動検出のサポートの構成
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945622(v=OCS.15)
ms:contentKeyID: 52056572
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 自動検出のサポートの構成

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server の Web サービスである **自動検出サービス**は、Lync Server 2010 の累積的な更新プログラム: 2011 年 11 月で初めて提供されました。この更新プログラムは、Lync Mobile クライアントの初期リリースに付属します。自動検出サービスでは、Mcx サービスと呼ばれるモビリティ サービスが公開されています。

すべてのクライアントがこの自動検出サービスを利用して、使用できるサービスや機能、およびサービスへの接続方法に関する情報を、完全修飾ドメイン名または Web URL (Uniform Resource Locator) 参照のどちらかを使って一元的に要求します。自動検出では複数の機能が公開されており、クライアントはそれぞれ、自身が利用できる機能に基づいて情報を要求します。たとえば、デスクトップ Lync 2013 クライアントの場合は、自動検出を使用して外部 Web サービスを確認しますが、モビリティ (Mcx) サービスを使用することはありません。クライアントを適切に定義して、クライアントが自身に合った機能を使用できるように、クライアントが効率的に自動検出エントリを検出および使用できるようにするシナリオを定義することをお勧めします。自動検出を使用する展開では、リバース プロキシによって Lync Server Web サービスが発行されていなければなりません。また、DNS レコードが Lync Server 自動検出サービスと Lync Server Web サービスの DNS クエリを解決するように構成され、さらに、証明書サービスが特定のシナリオに対して適切に構成されている必要があります。


> [!TIP]
> 自動検出要求/応答における要素の動作の技術的な詳細については、「<A href="lync-server-2013-understanding-autodiscover.md">自動検出について</A>」を参照してください。



次の情報と表では、自動検出サービスを完全かつ効果的に使用するのに必要な構成をシナリオごとに定義しています (存在する場合)。次のトピックの情報は Microsoft Lync Server 2013 にのみ適用されます。Lync Server 2010 のモビリティを計画する方法に関するガイダンスが必要な場合は、<http://go.microsoft.com/fwlink/?linkid=275113> を参照してください。Lync Server 2010 のモビリティの展開については、<http://go.microsoft.com/fwlink/?linkid=275114> を参照してください。

## このセクション中

  - [自動検出の DNS を構成する](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [自動検出用の証明書の構成](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [自動検出用のリバース プロキシの構成](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [ハイブリッド展開のための自動検出の構成](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

