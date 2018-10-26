---
title: 'Lync Server 2013: エンタープライズ VoIP のセキュリティおよび構成の前提条件'
TOCTitle: エンタープライズ VoIP のセキュリティおよび構成の前提条件
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48271360
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のエンタープライズ VoIP のセキュリティおよび構成の前提条件

 

_**トピックの最終更新日:** 2012-10-18_

インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。

## 管理者権限と証明書インフラストラクチャ

エンタープライズ VoIP の展開プロセス時に使用する次の管理者ユーザー グループと証明書インフラストラクチャで環境が構成されていることを確認します。

  - エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。

  - 構成タスクを実行する管理者に十分な権限があること。
    
      - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
      - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
      - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
    > [!NOTE]
    > 委任という手段を使用すると、リソースを不必要に開示することなく、Lync Server の展開に関与する管理者の数を増やすことができます。


  - マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    > [!NOTE]
    > Lync Server の証明書の要件の詳細については、「計画」ドキュメントの「<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 の証明書インフラストラクチャの要件</a>」を参照してください。


## ユーザー構成

フロントエンドの展開時に仲介サーバーと各フロントエンド プールまたは Standard Edition サーバーを併置した場合、エンタープライズ VoIP に必要なユーザー設定は、これらのサーバーの役割のファイルがインストールされるときに自動的に構成されています。

この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装する前にすべての主要電話番号を正規化 (適切な形式に) し、Lync Server コントロール パネルを使用して各ユーザーの **\[回線 URI\]** プロパティにコピーします。

> [!NOTE]
> エンタープライズ VoIP の展開に必要な主要電話番号の例については、「計画」のドキュメントにある「<a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 のダイヤル プランと正規化ルール</a>」の「<a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 のダイヤル プランと正規化ルール</a>」セクションを参照してください。


## 次のステップ: ファイルのインストールや PSTN 接続の構成

エンタープライズ VoIP のソフトウェアおよび環境の前提条件を確認したら、以下の情報を参照して次のいずれかの操作を実行できます。

  - 「[Lync Server 2013 仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)」の説明に従って、仲介サーバーをインストールします (ただし、併置するとフロントエンド プールまたは Standard Edition サーバーの展開プロセスの一部として仲介サーバーがインストールされるため、仲介サーバーまたはプールをスタンドアロンで展開する場合に限ります)。

  - 「[Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)」の説明に従って、エンタープライズ VoIP ユーザーの通話をルーティングするように設定の構成を開始します。

