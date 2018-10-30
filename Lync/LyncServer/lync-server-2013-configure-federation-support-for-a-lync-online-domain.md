---
title: Lync オンライン ドメインのフェデレーション サポートを構成する
TOCTitle: Lync オンライン ドメインのフェデレーション サポートを構成する
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48271418
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync オンライン ドメインのフェデレーション サポートを構成する

 

_**トピックの最終更新日:** 2012-11-01_

Microsoft Lync Online 2010 ユーザーとのフェデレーションを行うには、以下の手順を完了する必要があります。

  - Lync Online 2010 ユーザーのドメイン (例: contoso.onmicrosoft.com) に対するサポートを構成します。このドキュメントの「[Lync Online の顧客とのフェデレーションの前提条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)」セクションで説明したように、既にフェデレーションは組織で有効になっているはずです。フェデレーションを有効にするには、フェデレーション ドメインによってアクセス制御に使用されるメソッドを指定する必要があります。検出を使用するように組織を構成した場合は、組織の許可リストへのドメインの追加は省略できます。ドメインの検出を有効にしなかった場合は、許可されたドメインのリストに Lync Online ユーザーのドメイン名を追加する必要があります。ドメイン名を追加するには、Lync Server コントロール パネルを使用するか、**New-CSAllowedDomain** コマンドレットを実行します。ドメインの検出の有効化など、Lync Server コントロール パネルの使用の詳細については、「操作」のドキュメントの「[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)」を参照してください。**New-CSAllowedDomain** コマンドレットを使用してドメインを追加する方法の詳細については、「操作」のドキュメントの「[New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain)」を参照してください。
    
    > [!NOTE]
    > Lync Online ユーザーは複数のドメインを持つことができます。複数のドメインとのフェデレーションを行う場合は、フェデレーションをサポートするドメインごとにサポートを構成する必要があり、Lync Online ユーザーの管理者はフェデレーションの対象になるドメインごとにフェデレーションを有効にする必要があります。


  - フェデレーションを行う Lync Online 2010 ユーザー ドメインのホスティング プロバイダーのサポートを構成します。ホスティング プロバイダーのサポートを構成するには、このセクションの手順に従います。
    
    > [!NOTE]
    > この手順は、Lync Online ユーザーのドメインとのフェデレーションの場合にのみ必要であり、フェデレーション パートナーの場所に社内展開されたドメインとのフェデレーションには不要です。


## ホスティング プロバイダーのサポートを構成するには

1.  フロント エンド サーバーから、Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを作成および構成します。たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    上記の例では、次のパラメーターを設定しています。
    
      - **Identity** は、作成するホスティング プロバイダーの、一意の文字列値 からなる識別子を指定します。既存のプロバイダーがその ID で既に構成されている場合、このコマンドの実行は失敗します。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **VerificationLevel** は、メッセージがホスティング プロバイダーから送信されたことを確認するために、そのプロバイダーから送信されたメッセージの検証方法 (または検証の有無) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効かどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換できません。
    
      - **EnabledSharedAddressSpace** は、共有 SIP アドレス空間 (分割ドメイン) のシナリオで、ホスティング プロバイダーが使用されるかどうかを示します。
    
      - **HostsOCSUsers** は、ホスティング プロバイダーが Lync Server アカウントをホストするために使用されているかどうかを示します。**False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Lync Server トポロジ内にあるかどうかを示します。
    
    このコマンドレットの使用の詳細については、「操作」のドキュメントの「[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)」を参照してください。

