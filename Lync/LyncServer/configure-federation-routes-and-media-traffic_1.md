---
title: フェデレーション ルートとメディア トラフィックを構成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754963"
---
# <a name="configure-federation-routes-and-media-traffic"></a>フェデレーション ルートとメディア トラフィックを構成する

 


フェデレーションとは、別々の組織のユーザーがネットワーク境界を越えて通信することを許可する、複数の SIP ドメイン間での信頼関係のことです。 Lync Server 2013 パイロットプールに移行した後、Microsoft Office Communications Server 2007 R2 エッジサーバーのフェデレーションルートから Lync Server 2013 エッジサーバーのフェデレーションルートに移行する必要があります。

次の手順を使用して、Office Communications Server 2007 R2 エッジサーバーとディレクターから Lync Server 2013 エッジサーバーにフェデレーションルートとメディアトラフィックルートを移行し、単一サイトを展開します。


> [!IMPORTANT]  
> フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Office Communications Server 2007 R2 エッジサーバーのメンテナンスダウンタイムをスケジュールする必要があります。 また、この移行プロセスで機能が停止している間は、フェデレーション アクセスも使用できません。 ダウンタイムは、ユーザー アクティビティが最も少ない時間帯に予定してください。 また、ダウンタイムが発生することをエンド ユーザーに知らせる必要もあります。 組織の事情に応じて停止を計画し、適切に対応してください。




> [!IMPORTANT]  
> 従来の Office Communications Server 2007 R2 エッジサーバーが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスに同じ FQDN を使用するように構成されている場合、このセクションの手順を使用して、フェデレーション設定を Lync Server 2013 エッジサーバーに移行することはサポートされていません。 従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まず、すべてのユーザーを Office Communications Server 2007 R2 から Lync Server 2013 に移行してから、Lync Server 2013 エッジサーバーでフェデレーションを有効にする前に、Office Communications Server 2007 R2 エッジサーバーを使用停止にする必要があります。 詳細については、以下のトピックを参照してください。 
> <UL>
> <LI>
> <P><A href="move-remaining-users-to-lync-server-2013_1.md">残りのユーザーを Lync Server 2013 に移動する</A></P>
> <LI>
> <P>「サーバーとサーバーの役割を削除する」<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></P></LI></UL>




> [!IMPORTANT]  
> XMPP フェデレーションが Lync server 2013 エッジサーバーを経由してルーティングされている場合、従来の Office Communications Server 2007 R2 ユーザーは、すべてのユーザーが Lync Server 2013 に移動され、XMPP ポリシーと証明書が構成され、XMPP フェデレーションパートナーが Lync Server 2013 で構成されており、最後に DNS エントリが更新されます。



サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインする必要があります。 サーバーの役割を追加する適切なユーザー権限とアクセス許可を委任することもできます。 詳細については、「Standard Edition サーバーまたは Enterprise Edition server 展開ドキュメント」の「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。 他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a>Lync Server 2013 サイトから従来のフェデレーションの関連付けを削除するには

1.  トポロジ ビルダーを使用してパイロット プールを開きます。

2.  左ウィンドウで、サイト ノードに移動します。

3.  サイトを右クリックし、[**プロパティの編集**] をクリックします。

4.  左ウィンドウの [**フェデレーション ルート**] を選択します。

5.  [サイトのフェデレーション ルートの割り当て] で、[**SIP フェデレーションの有効化**] の横のチェック ボックスをオフにして、[**BackCompatSite**] を経由するフェデレーション　ルートを無効にします。
    
    ![[プロパティの編集] ダイアログ、フェデレーションルート](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[プロパティの編集] ダイアログ、フェデレーションルート")

6.  [**OK**] をクリックして、[プロパティの編集] ページを閉じます。

7.  [**トポロジ ビルダー**] で、最上位ノードの [**Lync Server**] を選択します。

8.  [**操作**] メニューの [**トポロジの公開**] をクリックし、ウィザードを完了します。

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>従来のエッジ サーバーをフェデレーションされていないエッジ サーバーとして構成するには

1.  [**トポロジ ビルダー**] の [**操作**] メニューの [**Office Communications Server 2007 R2 トポロジのマージ**] をクリックします。

2.  [**次へ**] をクリックして続行します。

3.  [**エッジ セットアップの指定**] で、フェデレーションに現在構成されている [**エッジ サーバーの内部 FQDN**] を選択し、[**変更**] をクリックします。
    
    ![OCS 2007 R2 トポロジのマージ、エッジセットアップの指定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 トポロジのマージ、エッジセットアップの指定")

4.  [**次へ**] をクリックし、[**外部エッジの指定**] ページが表示されるまで既定値を使用します。
    
    ![トポロジビルダー、外部エッジページの指定](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "トポロジビルダー、外部エッジページの指定")

5.  In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.
    

    > [!IMPORTANT]  
    > This step is important. You must clear this option to remove the legacy federation association.



6.  [**次へ**] をクリックし、ウィザードの残りのページで既定値を使用します。

7.  [**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。

8.  [**状態**] 列で、値が "**成功**" になっていることを確認し、[**完了**] をクリックしてウィザードを閉じます。

9.  [**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。

10. **公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。
    
    ![マージ後にサイトが表示されたトポロジビルダー](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "マージ後にサイトが表示されたトポロジビルダー")
    
    前の図に示したように、[ **サイトのフェデレーション ルートの割り当て**] の [**SIP federation**] (SIP フェデレーション) は [**無効**] に設定されています。

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a>Lync Server 2013 エッジ サーバーで証明書を構成するには

1.  従来の Office Communications Server 2007 R2 エッジサーバーから、秘密キーを使用して外部アクセスプロキシ証明書をエクスポートします。

2.  Lync Server 2013 エッジサーバーで、前の手順でアクセスプロキシの外部証明書をインポートします。

3.  エッジサーバーの Lync Server 2013 外部インターフェイスにアクセスプロキシの外部証明書を割り当てます。

4.  Lync Server 2013 エッジサーバーの内部インターフェイス証明書は変更しないでください。

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a>Office Communications Server 2007 R2 フェデレーション ルートを変更して Lync Server 2013 エッジ サーバーを使用するには

1.  Office Communications Server 2007 R2 Standard Edition サーバーまたはフロントエンドサーバーで、Office Communications Server 2007 R2 管理ツールを開きます。

2.  In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.

3.  [**フェデレーション**] タブをクリックします。

4.  チェック ボックスをオンにして、フェデレーションとパブリック IM 接続を有効にします。

5.  Lync Server 2013 エッジサーバーの FQDN を入力し、[ **OK]** をクリックします。
    
    ![OCS の [グローバルプロパティ]、[フェデレーション] タブ](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS の [グローバルプロパティ]、[フェデレーション] タブ")

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a>Lync Server 2013 エッジ サーバーのフェデレーションを有効にするには

1.  トポロジビルダーの左側のウィンドウで、[Lync Server 2013**エッジプール**] ノードに移動します。

2.  ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。
    

    > [!NOTE]  
    > フェデレーションは、単一のエッジプールに対してのみ有効にできます。 エッジ プールが複数ある場合は、フェデレーション エッジ プールとして使用するエッジ プールを 1 つ選択してください。



3.  [**全般**] ページで、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックスをオンにします。
    
    ![プロパティを編集、全般、エッジフェデレーションを有効にする](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "プロパティを編集、全般、エッジフェデレーションを有効にする")

4.  [**OK**] をクリックして、[プロパティの編集] ページを閉じます。

5.  次に、サイト ノードに移動します。

6.  サイトを右クリックし、[**プロパティの編集**] をクリックします。

7.  左ウィンドウで、[**フェデレーション ルート**] をクリックします。

8.  [**サイトのフェデレーションルートの割り当て**] で [ **SIP フェデレーションの有効化**] を選択し、一覧から [Lync server 2013 エッジサーバー] を選択します。

9.  [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。
    
    ![プロパティの編集、全般、エッジプールの関連付け](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "プロパティの編集、全般、エッジプールの関連付け")
    
    マルチサイト展開の場合は、この手順をサイトごとに実行します。

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a>Lync Server 2013 エッジ サーバーの送信メディア パスを構成するには

1.  **トポロジビルダー**で、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下にある Lync Server 2013 プールに移動します。

2.  プールを右クリックし、[**プロパティの編集**] をクリックします。

3.  [**関連付け**] セクションで、[**エッジ プールの関連付け (メディア コンポーネント用)**] チェック ボックスをオンにします。

4.  ドロップダウンボックスから、Lync Server 2013 エッジサーバーを選択します。
    
    ![[プロパティの編集] ダイアログ、エッジプールの関連付け](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[プロパティの編集] ダイアログ、エッジプールの関連付け")

5.  [**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。

## <a name="to-publish-edge-server-configuration-changes"></a>エッジ サーバーの構成の変更を公開するには

1.  [**トポロジ ビルダー**] で、最上位ノードの [**Lync Server**] を選択します。

2.  [**操作**] メニューの [**トポロジの公開**] を選択し、ウィザードを完了します。

3.  展開内のすべてのプールに対して Active Directory のレプリケーションが発生するのを待ちます。
    

    > [!NOTE]  
    > 次のメッセージが表示されることがあります。<BR><STRONG>警告: 複数のフェデレーション エッジ サーバーがトポロジに含まれています。この状態は、最新バージョンの製品への移行中に発生することがあります。その場合、1 つのエッジ サーバーのみがフェデレーション用に実際に使用されます。外部 DNS SRV レコードが正しいエッジ サーバーを指していることを確認してください。複数のフェデレーション エッジ サーバーを (移行シナリオ以外で) 同時にアクティブにして展開する場合は、すべてのフェデレーション パートナーが Office Communications Server 2007 R2 または Lync Server を使用していることを確認してください。また、外部 DNS SRV レコードにすべてのフェデレーション対応エッジ サーバーがリストされていることを確認してください。 </STRONG><BR>この警告は予期されるものであり、無視してもかまいません。



## <a name="to-verify-federation-and-remote-access-for-external-users"></a>外部ユーザーのフェデレーションとリモート アクセスを確認するには

1.  Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。

2.  フェデレーションとリモート アクセスの状態を確認するには、コマンド ラインから次のように入力します。
    
        Get-CsAccessEdgeConfiguration

3.  フェデレーションとリモート アクセスを有効化するには、コマンド ラインから次のように入力します。
    
        Set-CsAccessEdgeConfiguration
    
    これらのコマンドレットの詳細については、以下のトピックを参照してください。 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))および[set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。

4.  Lync Server 2013 エッジサーバーをオンラインにし、フェデレーションと外部アクセスをテストする前に、レプリケーションが完了するまで待機します。

## <a name="to-configure-lync-server-2013-edge-server"></a>Lync Server 2013 エッジ サーバーを構成するには

1.  すべての Lync Server 2013 エッジサーバーをオンラインにします。

2.  外部ファイアウォールのルーティングルールまたはロードバランサー機器の設定を更新して、外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを従来のエッジサーバーではなく Lync Server 2013 エッジサーバーに送信します。
    

    > [!NOTE]  
    > If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.



3.  次に、各エッジサーバーコンピューターから**Lync Server アクセスエッジ**を停止します。

4.  従来の各エッジサーバーコンピューターから、[**管理ツール**] から [**サービス**] アプレットを開きます。

5.  サービス リストで、[**Office Communications Server アクセス エッジ**] を見つけます。

6.  サービス名を右クリックし、[**停止**] を選択してサービスを停止します。

7.  スタートアップの種類を [**無効**] に設定します。

8.  [**OK**] をクリックして、[**プロパティ**] ウィンドウを閉じます。

## <a name="to-test-connectivity-of-external-users-and-external-access"></a>外部ユーザーの接続と外部アクセスをテストするには

  - 少なくとも1つのフェデレーションドメインのユーザー。 Lync Server 2013 上の内部ユーザーと Office Communications Server 2007 R2 のユーザー。 インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。

  - 組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーが、Lync Server 2013 上のユーザーおよび Office Communications Server 2007 R2 上のユーザーと通信します。

  - 匿名ユーザーが会議に参加できることを確認します。

  - リモートユーザーアクセスを使用して Office Communications Server 2007 R2 でホストされているユーザー (Office Communications Server 2007 R2 から VPN を使用しない)、Lync Server 2013 のユーザー、および Office Communications Server 2007 R2 上のユーザー。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

  - Lync server 2013 上のユーザーと、Office Communications Server 2007 R2 上のユーザーとのリモートユーザーアクセスを使用して、Lync server 2013 でホストされているユーザー (イントラネットの外部からの Lync Server 2013 へのログイン、および VPN を使用しない)。 IM、プレゼンス、A/V、およびデスクトップ共有をテストします。

