---
title: ハイブリッドおよび分割ドメイン - 自動検出
TOCTitle: ハイブリッドおよび分割ドメイン - 自動検出
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945652(v=OCS.15)
ms:contentKeyID: 52056704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ハイブリッドおよび分割ドメイン - 自動検出

 

_**トピックの最終更新日:** 2013-02-14_

共有済みの SIP アドレス スペースは、"分割ドメイン" 展開または "ハイブリッド" 展開とも呼ばれる構成で、ユーザーは社内展開とオンライン展開をまたいで展開されます。この構成では、ホーム サーバーの設置場所 (社内またはオンラインのどちらであるか) に関係なく、展開にログインしたユーザーは、そのホーム サーバーの設置場所にリダイレクトされることが望まれます。これを達成するために、Lync Server 2013 の自動検出を使用して、オンライン ユーザーはオンライン トポロジにリダイレクトされます。このリダイレクトを行うには、Lync Server 管理シェルで **Get-CsHostingProvider** コマンドレットおよび **Set-CsHostingProvider** コマンドレットを使用して自動検出の Uniform Resource Locator (URL) を構成します。

## 分割ドメイン展開でのモビリティ

次の展開属性を収集して記録する必要があります。

  - Lync Server 管理シェルで、次のように入力します。
    
        Get-CsHostingProvider

  - 実行結果から、**ProxyFQDN** 属性を持つオンライン プロバイダー (たとえば、sipfed.online.lync.com) を見つけます。

  - ProxyFQDN の値を記録します。

  - 社内の Lync Server コントロール パネルでフェデレーションを有効にします。オンライン プロバイダーとのフェデレーションが可能になります。

  - オンライン プロバイダーに対してフェデレーションを有効にします。既定では、ドメイン フェデレーションに対してすべてのオンライン ユーザーが有効になり、すべてのドメインと通信できます。

  - 禁止ドメインと許可ドメインを定義する場合は、明示的に許可するドメイン、または明示的に禁止するドメインを決めます。

  - オンライン フェデレーションの場合、ファイアウォールの例外、証明書、および DNS ホスト (A、または IPv6 を使用する場合は AAAA) レコードを計画する必要があります。また、フェデレーション ポリシーを構成する必要もあります。詳細については、「[Lync Server と Office Communications Server のフェデレーションの計画](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)」を参照してください。

