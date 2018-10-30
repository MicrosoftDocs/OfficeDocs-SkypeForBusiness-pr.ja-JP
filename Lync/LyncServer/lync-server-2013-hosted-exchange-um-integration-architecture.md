---
title: 'Lync Server 2013: Hosted Exchange UM 統合のアーキテクチャ'
TOCTitle: Hosted Exchange UM 統合のアーキテクチャ
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48271057
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Hosted Exchange UM 統合のアーキテクチャ

 

_**トピックの最終更新日:** 2012-09-25_

Lync Server 2013 ExUM ルーティング アプリケーションは、内部設置型 Exchange ユニファイド メッセージング (UM) 展開環境との統合を、1 社のサービス プロバイダーがホストする Exchange UM と共に、または 2 社のサービス プロバイダーがホストする Exchange UM の組み合わせと共にサポートします。 以下の図に、3 つすべての展開シナリオを示します。

**内部設置型 Exchange UM 展開環境と 2 社の Hosted Exchange プロバイダーとの統合**

![社内の Lync Server Exchange UM 展開](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "社内の Lync Server Exchange UM 展開")

次のモードがサポートされています。

  - **内部設置型展開 :** Lync Server 2013 および Exchange UM は、企業内のローカル サーバーに展開されます。

  - **構内間の展開 :** Lync Server 2013 は企業内のローカル サーバーに展開され、Exchange UM は Microsoft Exchange Online データ センターなどのオンライン サービス プロバイダーの設備にホストされます。

  - **混合展開 :** Lync Server 2013 展開環境には、社内のローカル Exchange サーバーに属するユーザー メールボックスも、Hosted Exchange サービス データ センターに属するメールボックスも存在します。
    
    > [!NOTE]
    > 混合展開は、評価のためにユーザーを Hosted Exchange UM に段階的に移行する場合の暫定的なソリューションとして、または、一部のユーザーの Exchange UM サービスを社外に移行した後で、他のユーザーの Exchange UM サービスを内部設置型で維持する場合の恒久的なソリューションとして使用できます。


## 共有 SIP アドレス スペース

Lync Server 2013 と内部設置型 Exchange UM 展開環境を統合する場合は、Exchange UM Active Directory Domain サービス オブジェクトの読み取りアクセス許可を Lync Server 2013 に付与します。 ただし、Lync Server 2013 と Exchange UM は、相互に信頼のない個別のフォレストにインストールされるため、このアプローチは Hosted Exchange UM との統合では使用できません。

Lync Server 2013 と Hosted Exchange UM を統合するには、*共有 SIP アドレス スペース*を構成する必要があります。この構成では、同一の SIP ドメイン アドレス スペースは、Lync Server 2013 と Hosted Exchange UM サービス プロバイダーの両方が使用できます。

> [!NOTE]
> 共有 SIP アドレス スペースの使用は、一部のユーザーが内部設置型展開環境に存在し、その他のユーザーがホスト型展開環境 (Lync Server 2013 など) に存在する構内間 Lync Online 環境で使用されるアプローチと似ています。SIP ドメインは、2 者間で分割されています。Lync Server 2013 を Hosted Exchange UM と統合する場合は、共有 SIP アドレス スペースに Exchange UM サービス プロバイダーを必ず含めてください。


Exchange UM サービス プロバイダーとの統合用に共有 SIP アドレス スペースを構成するには、エッジ サーバーを以下のように構成する必要があります。

1.  エッジ サーバーでフェデレーションを構成するには、**Set-CsAccessEdgeConfiguration** コマンドレットを実行して、以下のパラメーターを設定します。
    
      - **UseDnsSrvRouting** は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。
    
      - **AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。 このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。
    
      - **EnablePartnerDiscovery** は、Lync Server 2013 が DNS レコードを使用して、Active Directory によって許可されたドメイン リストにないパートナー ドメインを検出するかどうかを指定します。 False に設定された場合、Lync Server 2013 は、許可されたドメイン リストにあるドメインに対してのみフェデレーションを行います。DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。 ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。

2.  中央管理ストアをエッジ サーバーにレプリケートして、レプリケーションを確認します。詳細については、「展開」のドキュメントの「[エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)」を参照してください。

3.  **New-CsHostingProvider** コマンドレットを実行して以下のパラメーターを設定することで、*ホスティング プロバイダー*をエッジ サーバー上で構成します。
    
      - **Identity** は、作成しているホスティング プロバイダーの一意の文字列値からなる識別子 (**Hosted Exchange UM** など) を指定します。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 **True** に設定する必要があります。
    
      - **EnabledSharedAddressSpace** は、ホスティング プロバイダーが共有 SIP アドレス スペース シナリオで使用されるかどうかを示します。**True** に設定する必要があります。
    
      - **HostsOCSUsers** は、ホスティング プロバイダーが Lync Server 2013 アカウントをホストするために使用されているかどうかを示します。 **False** に設定する必要があります。
    
      - **ProxyFQDN** は、ホスティング プロバイダーによって使用されるプロキシ サーバーの完全修飾ドメイン名 (FQDN) (**proxyserver.fabrikam.com** など) を指定します。 この情報については、ホスティング プロバイダーに問い合わせてください。この値は変更できません。 ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Lync Server 2013 トポロジ内に含まれているかどうかを示します。**False** に設定する必要があります。

