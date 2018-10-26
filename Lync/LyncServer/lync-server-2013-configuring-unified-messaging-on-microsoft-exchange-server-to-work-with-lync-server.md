---
title: "Lync Server 2013: Lync Server と連動させる Exchange Server のユニファイド メッセージングの構成"
TOCTitle: Lync Server 2013 と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48271121
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 と連動させるための Microsoft Exchange Server のユニファイド メッセージングの構成

 

_**トピックの最終更新日:** 2016-12-08_


> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) を使用して、通話応答、Outlook Voice Access、または自動応答サービスを エンタープライズ VoIP ユーザーに提供する場合は、「計画」のドキュメントの「<A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013 での Exchange ユニファイド メッセージング統合の計画</A>」の情報を参照して、このセクションの手順に従ってください。



エンタープライズ VoIP と連携するように Exchange ユニファイド メッセージング (UM) を構成するには、以下のタスクを実行する必要があります。

  - Exchange ユニファイド メッセージング (UM) サービスを実行しているサーバーで証明書を構成する
    
    > [!NOTE]
    > すべてのクライアント アクセス サーバーとメールボックス サーバーをすべての UM SIP URI ダイヤル プランに追加します。追加しない場合、発信通話ルーティングは期待どおりに機能しなくなります。


  - 1 つ以上の UM SIP URI ダイヤル プランと、必要に応じてそのサブスクライバー アクセス用の電話番号を作成してから、対応する Lync Server のダイヤル プランを作成します。

  - **exchucutil.ps1** スクリプトを使用して、以下の操作を行います。
    
      - UM IP ゲートウェイを作成します。
    
      - UM ハント グループを作成します。
    
      - UM Active Directory ドメイン サービス オブジェクトの読み取りアクセス許可を Lync Server 2013 に付与します。

  - UM 自動応答オブジェクトを作成する

  - サブスクライバー アクセス オブジェクトを作成します。

  - 各ユーザーの SIP URI を作成し、ユーザーを UM SIP URI ダイヤル プランと関連付けます。

## 要件と推奨事項

最初に、このセクションのドキュメントでは、Exchange 2013 の役割としてクライアント アクセスおよびメールボックスを展開していることを前提とします。Microsoft Exchange Server 2013 では、Exchange UM がこれらのサーバー上でサービスとして実行されます。

Exchange 2013 の展開の詳細については、Exchange 2013 の TechNet ライブラリ ([http://go.microsoft.com/fwlink/?linkid=266637\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=266637%26clcid=0x411)) を参照してください。

以下の点にも注意してください。

  - Exchange UM が複数のフォレストにインストールされている場合は、各 UM フォレストに対して Exchange Server の統合ステップを実行する必要があります。また、各 UM フォレストは、Lync Server 2013 が展開されているフォレストを信頼するように構成し、Lync Server 2013 が展開されているフォレストは、各 UM フォレストを信頼するように構成する必要があります。

  - 統合ステップは、ユニファイド メッセージング サービスが実行されている Exchange Server の役割と、Lync Server 2013 を実行しているサーバーの両方で実行されます。Exchange Server ユニファイド メッセージングの統合ステップを実行してから、Lync Server 2013 の統合ステップを実行してください。
    
    > [!NOTE]
    > 実行する統合ステップ、サーバー、および管理者の役割の組み合わせについては、「<a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス</a>」を参照してください。


Exchange UM を実行している各サーバーに、以下のツールが用意されている必要があります。

  - Exchange 管理シェル

  - **exchucutil.ps1** スクリプト。このスクリプトは以下のタスクを実行します。
    
      - 各 Lync Server 2013 の UM IP ゲートウェイを作成します。
    
      - 各ゲートウェイのハント グループを作成します。 各ハント グループのパイロット ID によって、ゲートウェイに関連付けられている フロント エンド プールまたは Standard Edition サーバーで使用される UM SIP URI ダイヤル プランが指定されます。
    
      - Active Directory ドメイン サービス の Exchange UM オブジェクトの読み取りアクセス許可を Lync Server 2013 に付与します。

## このセクション中

  - [Microsoft Exchange Server ユニファイド メッセージングを実行しているサーバーでの証明書の構成](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Lync Server 2013 での Microsoft Exchange のユニファイド メッセージングの構成](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

