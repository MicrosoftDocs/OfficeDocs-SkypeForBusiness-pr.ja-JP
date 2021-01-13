---
title: Skype for Business Server 2015 の環境要件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: '概要: Skype for Business Server 2015 のサーバー以外の要件を構成します。 Active Directory、DNS、Certs、Fileshares など、展開を行う前に構成する必要があるさまざまなものがあります。'
ms.openlocfilehash: 83e01cec8bea5a45debadcf8ef9167ddd53b6a46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832137"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の環境要件
 
**概要:** Skype for Business Server 2015 のサーバー以外の要件を構成します。 Active Directory、DNS、Certs、Fileshares など、展開を行う前に構成する必要があるさまざまなものがあります。
  
Skype for Business Server 2015 の環境要件は何ですか? このトピックでは、サーバーに直接関連していないものをすべて取り入れたので、クリックする必要がなほどではありません。 サーバーの前提条件を探している場合は[、Skype for Business Server 2015](server-requirements.md)のドキュメントのサーバー要件を確認[](../../plan-your-deployment/network-requirements/network-requirements.md)できます。ネットワーク計画も個別に文書化されています。 それ以外の場合、この記事では次の情報を確認できます。
  
- [Active Directory](environmental-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](environmental-requirements.md#DNS)
  
- [証明書](environmental-requirements.md#Certs)
  
- [ファイル共有](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーとサービスの多くの構成データは Skype for Business Server 2015 の中央管理ストアに保存されていますが、Active Directory には次の情報が保存されています。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||Lync Server 2013 および Lync Server 2010 の拡張機能。サポートされている以前のバージョンとの下位互換性を維持します。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (応答グループ アプリケーションや会議アテンダント アプリケーションなど)。  <br/> |
||下位互換性のために公開されたデータ。  <br/> |
||中央管理ストアのサービス コントロール ポイント (SCP)。  <br/> |
||Kerberos 認証アカウント (オプションのコンピューター オブジェクト)。  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用 OS

では、どのドメイン コントローラー OS を使用できますか。 次の一覧があります。

- Windows Server 2019 (Skype for Business Server 2015 の累積的な更新プログラム 5 以降が必要)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
次に、Skype for Business Server 2015 を展開するドメインのドメイン機能レベルと、Skype for Business Server 2015 を展開するフォレストのフォレスト機能レベルは、次のいずれかを指定する必要があります。

- Windows Server 2019 (Skype for Business Server 2015 の累積的な更新プログラム 5 以降が必要)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
これらの環境で読み取り専用ドメイン コントローラーを使用できますか。 Skype for Business Server と同じサイトで利用可能な書き込み可能なドメイン コントローラーがある限りは確かです。
  
次に、Skype for Business Server 2015 が単一ラベル付きドメインをサポートしないという点を知る必要があります。 何ですか? contoso.local というラベルのルート ドメインがある場合は、問題ありません。 local という名前のルート ドメインがある場合、それは機能しなく、その結果としてサポートされません。 この詳細については、このサポート技術情報 [の記事で少し詳しい情報を書かれています](https://support.microsoft.com/kb/300684/en-us)。
  
Skype for Business Server 2015 では、ドメイン名の変更もサポートされていません。 If you've really got to do that, then you'll need to uninstall Skype for Business Server 2015, do the domain rename, and then reinstall Skype for Business Server 2015.
  
最後に、DS 環境でロックダウンされたドメインAD処理している可能性があります。これは問題です。 この種の環境に Skype for Business Server 2015 を展開する方法の詳細については、「展開」のドキュメントを参照してください。
  
### <a name="ad-topologies"></a>AD トポロジ

Skype for Business Server 2015 でサポートされるトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用する Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
    
- Skype for Business Online と Azure Active Directory Connect を使用するリソース フォレスト トポロジ内の複数のフォレスト
    
環境に含めるトポロジや、Skype for Business Server 2015 をインストールする前に設定する必要がある可能性があるトポロジを判断するのに役立つ図と説明があります。 シンプルに保つには、次のキーも含めておく必要があります。
  
![The is a key to the icons used for Skype for Business topology diagrams](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![単一ドメインを持つ Active Directory 単一フォレストの図](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これよりも簡単には行えなく、単一のドメイン フォレストです。これは一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一フォレスト、単一ツリー、および複数のドメインの図](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は 1 つのフォレストを示していますが、1 つ以上の子ドメインもあります (この具体的な例には 3 つがあります)。 そのため、ユーザーが作成されるドメインは、Skype for Business Server 2015 が展開されているドメインとは異なる場合があります。 この問題を心配する理由 Skype for Business Server フロント エンド プールを展開する場合、そのプール内のすべてのサーバーが 1 つのドメイン内に配置されている必要がある点に注意してください。 Skype for Business Server による Windows ユニバーサル管理者グループのサポートを通じて、クロスドメイン管理を行える。
  
上の図に戻って、1 つのドメインのユーザーが、子ドメインに存在する場合でも、同じドメインまたは異なるドメインから Skype for Business Server プールにアクセスできるのを確認できます。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![1 つのフォレスト、複数のツリー、名前空間の不一部の図](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図に似たトポロジが用意されている可能性があります。フォレストは 1 つですが、そのフォレスト内には複数のドメインが含まれるので、別の AD 名前空間があります。 その場合、この図は、Skype for Business Server 2015 にアクセスする 3 つの異なるドメインのユーザーがいます。 実線は、ユーザーが自分のドメイン内の Skype for Business Server プールにアクセスしているのに対し、破線は別のツリー内のプールに完全に移動する場合を示します。
  
ご覧のように、同じドメイン、同じツリー、または別のツリーのユーザーは、プールに正常にアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジ内の複数のフォレストの図](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 は、中央フォレスト トポロジで構成された複数のフォレストをサポートします。 それが確実な場合、トポロジ内の中央フォレストは、その中のオブジェクトを使用して他のフォレストのユーザーを表し、フォレスト内の任意のユーザーのユーザー アカウントをホストします。
  
これはどのように機能しますか? ディレクトリ同期製品 (Forefront Identity Manager、FIM など) は、存在する組織のユーザー アカウントを管理します。 フォレストからアカウントが作成または削除されると、その変更は中央フォレスト内の対応する連絡先に同期されます。
  
明らかに、AD インフラストラクチャをこのトポロジに移行する場合は簡単ではない可能性がありますが、既にこのトポロジを使用している場合、またはフォレスト インフラストラクチャを計画している場合は、この方法が最適です。 1 つのフォレスト内で Skype for Business Server 2015 の展開を集中管理しながら、ユーザーは任意のフォレスト内の他のユーザーの検索、通信、およびプレゼンスの表示を行えます。 すべてのユーザー連絡先の更新は、同期ソフトウェアを使用して自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ内の複数のフォレストの図](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソース フォレスト トポロジもサポートされています。フォレストは、Microsoft Exchange Server や Skype for Business Server 2015 など、サーバー アプリケーションの実行専用です。 このリソース フォレストは、アクティブなユーザー オブジェクトの同期された表現もホストしますが、ログオンが有効なユーザー アカウントはありません。 そのため、リソース フォレストは、ユーザー オブジェクトが存在する他のフォレストの共有サービス環境であり、リソース フォレストとフォレスト レベルの信頼関係があります。
  
このExchange Server Skype for Business Server と同じリソース フォレストまたは別のフォレストに展開できます。
  
この種類のトポロジで Skype for Business Server 2015 を展開するには、ユーザー フォレスト内のユーザー アカウントごとに、無効にされたユーザー オブジェクトをリソース フォレストに 1 つ作成します (Microsoft Exchange Server が環境内に既に存在する場合は、これが実行される可能性があります)。 その後、ディレクトリ同期ツール (Forefront Identity Manager や FIM など) を使用して、ユーザー アカウントをライフ サイクルを通じて管理する必要があります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Skype for Business リソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは、Skype for Business リソース フォレスト トポロジの複数フォレストで説明 [されているトポロジに似ています](environmental-requirements.md#BKMK_multipleforestopology)。
  
このトポロジには 1 つ以上のユーザー フォレストが含まれています。Skype for Business Server は専用のリソース フォレストに展開されます。 Exchange Server同じリソース フォレストまたは別のフォレストにオンプレミスで展開し、Exchange Online とのハイブリッド用に構成したり、メール サービスが Exchange Online によってオンプレミス アカウント専用に提供される場合があります。 このトポロジで使用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online と Azure Active Directory Connect を使用するリソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つのAD、1 つのユーザー フォレストと 1 つのリソース フォレストを示します。 2 つのフォレストは信頼関係を持っています。 Azure AD Connect を使用して、Microsoft 365 または Office 365 と同期されます。 すべてのユーザーは、Microsoft 365 または Office 365 経由で Skype for Business に対して有効になります。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、複数のフォレストがオンプレミスで、リソース フォレスト トポロジを備えます。 Active Directory フォレスト間には完全な信頼関係があります。 Azure Active Directory Connect ツールは、オンプレミスのユーザー フォレストと Microsoft 365 または Office 365 の間でアカウントを同期するために使用されます。
  
 組織には Microsoft 365 または Office 365 もあります。 [また、Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) を使用してオンプレミス アカウントを Microsoft 365 または Office 365 と同期します。 Skype for Business が有効になっているユーザーは、Microsoft 365 または Office 365 および Skype for Business Online 経由で有効になります。 Skype for Business Server はオンプレミスで展開されません。
  
シングル サインオン認証は、ユーザー フォレストにある Active Directory フェデレーション サービス ファームによって提供されます。
  
このシナリオでは、Exchange オンプレミス、Exchange Online、ハイブリッド Exchange ソリューションの展開、または Exchange の展開がサポートされていません。 (図は Exchange オンプレミスのみを示していますが、他の Exchange ソリューションも完全にサポートされています)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソース フォレスト トポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1 つ以上のオンプレミス ユーザー フォレストがいて、Skype for Business が専用リソース フォレストに展開され、Skype for Business Online とのハイブリッド モード用に構成されます。 Exchange Server同じリソース フォレストまたは別のフォレストにオンプレミスで展開し、Exchange Online とのハイブリッド用に構成できます。 または、電子メール サービスは、Exchange Online によってオンプレミス アカウントに対して排他的に提供される場合があります。
  
詳細については、「ハイブリッド [Skype for Business 用に複数フォレスト環境を構成する」を参照してください](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 では、次の理由により DNS が必要です。
  
- DNS により、Skype for Business Server 2015 は内部サーバーまたはプールを検出でき、サーバー間通信が可能になります。
    
- DNS を使用すると、クライアント コンピューターは SIP トランザクションに使用されているフロントエンド プールまたは Standard Edition サーバーを検出できます。
    
- 会議の簡易 URL を、それらの会議をホストしているサーバーに関連付ける。
    
- DNS を使用すると、外部ユーザーとクライアント コンピューターは、インスタント メッセージング (IM) または会議用にエッジ サーバーまたは HTTP リバース プロキシに接続できます。
    
- これにより、ログインしていない統合コミュニケーション (UC) デバイスは、更新プログラムを取得してログを送信するために、デバイス更新 Web サービスを実行しているフロントエンド プールまたは Standard Edition サーバーを検出できます。
    
- DNS を使用すると、モバイル クライアントは、ユーザーがデバイス設定に URL を手動で入力する必要なしに、Web サービス リソースを自動的に検出できます。
    
- また、DNS 負荷分散で使用されます。
    
Skype for Business Server 2015 は国際化ドメイン名 (IDN) をサポートしません。
  
また、DNS 内の任意の名前は、Skype for Business Server 2015 で使用されている任意のサーバーで構成されているコンピューター名と同じである点に注意することが非常に重要です。 具体的には、環境内に短い名前を付けず、トポロジ ビルダー用の FQDN が必要です。
  
これは、ドメインに既に参加している任意のコンピューターに対して論理的に見えるようですが、ドメインに参加していないエッジ サーバーがある場合は、ドメイン サフィックスを付けない短い名前の既定の名前を持つ場合があります。 DNS またはエッジ サーバー、または Skype for Business Server 2015 サーバーまたはプールのどちらでも、この問題が当てはかからずにしてください。
  
また、Unicode 文字やアンダースコアは使用しません。 標準文字 (A ~ Z、a ~ z、0 ~ 9、およびハイフン) は、外部 DNS および公的な証明書機関でサポートされる文字です (証明書の SN に FQDN を割り当てる必要があります。忘れないでください)、この点を念頭に置いて名前を付けても、大きな不満を感じることはできません。
  
ネットワークの DNS 要件の詳細については、「計画」のドキュメント[](../../plan-your-deployment/network-requirements/network-requirements.md)の「ネットワーク」セクションを参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開する前に実行できる最も重要な点の 1 つは、証明書が正しく用意されている必要があるという点です。 Skype for Business Server 2015 には、トランスポート層セキュリティ (TLS) 接続と相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) が必要です。 基本的に、標準化された方法で安全に通信するために、Skype for Business Server は、Ca (Certificate Authorities) によって発行された証明書を使用します。
  
次に、Skype for Business Server 2015 で証明書を使用する機能の一部を示します。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションおよび Outlook Web Access (OWA) と会話する
    
そのため、証明書の計画は必要です。 次に、証明書を要求するときに注意する必要があるいくつかの項目の一覧を見てみます。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書は、オペレーティング システムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Skype for Business Server 2015 は、SHA-1 および SHA-2 スイートのダイジェスト サイズ (224、256、384、512 ビット) をサポートし、オペレーティング システムの要件を満たすか、または超えています。
    
- 自動登録は、Skype for Business Server 2015 を実行している内部サーバーでサポートされています。
    
- 自動登録は、Skype for Business Server 2015 エッジ サーバーではサポートされていません。
    
- Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。
    
> [!NOTE]
> KB922706 は、Windows Server 2003 証明書サービス Web 登録に対する Web 証明書の登録に関する問題の解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して Windows Server 2003 CA から証明書を要求することはできません。 
  
> [!NOTE]
> RSの(エラー 3657)、およびこの署名アルゴリズムの使用はサポートされていないため、ログインおよび呼び出し転送の問題などの問題が発生する可能性があります。 

> [!NOTE]
> Skype for Business Server 2015 は CNG 証明書をサポートしません。
  
- 暗号化キーの長さ 1024、2048、および 4096 がサポートされています。 2048 以上のキーの長さを推奨します。
    
- 既定のダイジェスト (ハッシュ署名) アルゴリズムは RSA です。 またECDH_P256、ECDH_P384、およびECDH_P521アルゴリズムもサポートされています。
    
そのため、CA から証明書を要求する場合には、さまざまな快適さレベルについて考える必要があります。 計画を可能な限り簡単に行う方法については、以下のガイダンスを参照してください。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバーの証明書

ほとんどの内部サーバーには証明書が必要です。ほとんどの場合、内部 CA (ドメイン内の CA) から証明書を取得します。 必要に応じて、外部 CA (インターネット上にある CA) からこれらの証明書を要求できます。 どのパブリック CA にアクセスする必要があるのか疑問に思う場合は、統合コミュニケーション証明書パートナーの一覧 [を確認](/SkypeForBusiness/certification/services-ssl) できます。
  
また、Skype for Business Server 2015 が他のアプリケーションやサーバー (skype for Business Server 2015 など) と通信する場合にも、証明書Microsoft Exchange Server。 これは明らかに、これらの他のアプリやサーバーがサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2015 および他の Microsoft 製品は、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 If you're interested in this, we have an additional planning article for OAuth and Skype for Business Server 2015.
  
Skype for Business Server 2015 には、SHA-256 暗号化ハッシュ関数を使用して署名された証明書 (不要) のサポートも含まれています。 SHA-256 を使用した外部アクセスをサポートするには、SHA-256 を使用してパブリック CA によって外部証明書を発行する必要があります。
  
簡単に実行するために、Standard Edition サーバー、フロントエンド プール、その他の役割の証明書要件を次の表に示します。架空の contoso.com は例として使用されています (環境に他の機能を使用している可能性があります)。 これらはすべて標準の Web サーバー証明書で、エクスポートできないプライベート キーを使用します。 次の点に注意してください。
  
- 証明書ウィザードを使用して証明書を要求すると、サーバー拡張キー使用法 (EKU) が自動的に構成されます。
    
- 各証明書の分名は、コンピューター ストア内で一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの代替名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。  <br/> ウィザードは、セットアップ中に指定した SIP ドメインを検出し、自動的にサブジェクトの代替名として追加します。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じ)  <br/> AND  <br/> • 簡単な URL を満たす  <br/> • ダイヤルイン簡易 URL  <br/> • 管理簡易 URL  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN= \* .contoso.com  <br/> |トポロジ ビルダーで内部 Web FQDN を上書きできない。  <br/> 複数の簡単な Meet URL がある場合は、すべての URL を SAN として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルイン簡易 URL  <br/> • SIP ドメインごとに簡単な URL を満たす  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |複数の簡単な Meet URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
Enterprise Edition フロントエンド プール内のフロントエンド サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じではない)  <br/> • サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> • 簡単な URL を満たす  <br/> • ダイヤルイン簡易 URL  <br/> • 管理簡易 URL  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN= \* .contoso.com  <br/> |複数の簡単な Meet URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルイン簡易 URL  <br/> • 管理簡易 URL  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |複数の簡単な Meet URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |ディレクター プール  <br/> |ディレクターの FQDN、ディレクター プールの FQDN。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS 照合が必要な場合は、sip.sipdomain のエントリも必要です (使用する SIP ドメインごとに)。  <br/> |pool.contoso.com;SAN=dir01.contoso.com  <br/> このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じ)  <br/> • サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> • 簡単な URL を満たす  <br/> • ダイヤルイン簡易 URL  <br/> • 管理簡易 URL  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • SIP ドメインごとに簡単な URL を満たす  <br/> • ダイヤルイン簡易 URL  <br/> OR  <br/> • 簡易 URL のワイルドカード エントリ  <br/> |ディレクターの外部 Web FQDN は、フロントエンド プールまたはフロントエンド サーバーとは異なる必要があります。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
スタンドアロン仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net;SAN=medsvr-pool.contoso.net;SAN=medsvr01.contoso.net  <br/> |
   
存続可能ブランチ アプライアンスの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |アプライアンスの FQDN  <br/> |SIP。\<sipdomain\> (必要なエントリは SIP ドメインごとに 1 つのみです)  <br/> |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>常設チャット サーバーの証明書

常設チャット サーバーをインストールする場合、Skype for Business Server 2015 の内部サーバーで使用される証明書と同じ CA によって発行された証明書が必要になります。 これは、ファイルのアップロード/ダウンロードのために常設チャット Web サービスを実行している各サーバーに対して実行する必要があります。 常設チャットのインストールを開始する前に、必要な証明書を使用することを強くお勧めします。また、CA が外部の場合はさらに多くのことをお勧めします (これらの証明書の発行には少し時間がかかる場合があります)。
  
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセスの証明書 (エッジ)

Skype for Business Server 2015では、アクセスおよび Web 会議エッジの外部インターフェイスに単一のパブリック証明書を使用し、音声ビデオ認証サービスをサポートしています。音声ビデオ認証サービスはすべてエッジ サーバー経由で提供されます。 エッジの内部インターフェイスは、通常、内部 CA によって発行されたプライベート証明書を使用しますが、信頼できる CA からの証明書である場合は、この場合もパブリック証明書を使用できます。
  
リバース プロキシ (RP) もパブリック証明書を使用し、RP からクライアントへの通信、および RP から内部サーバーへの通信を HTTP (より正確には TLS over HTTP) を使用して暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティの証明書

モビリティを展開し、モバイル クライアントの自動検出をサポートしている場合は、モバイル クライアントからのセキュリティで保護された接続をサポートするために、証明書に追加のサブジェクト代替名エントリを含める必要があります。
  
どの証明書ですか? 証明書の自動検出には、次の SAN 名が必要です。
  
- ディレクター プール
    
- フロント エンド プール
    
- リバース プロキシ
    
以下の各表に詳細を示します。
  
ここで、少し事前計画を立てたら良い場所ですが、モビリティを展開せずに Skype for Business Server 2015 を展開した場合、環境内に証明書が既に存在する場合は、この点が大きな問題になります。 通常、内部 CA を介して証明書を再発行するのは非常に簡単ですが、パブリック CA からのパブリック証明書では、もう少しコストがかかる可能性があります。
  
この点を確認し、多くの SIP ドメイン (SANS の追加コストを高くする) がある場合は、HTTPS (既定の構成) を使用する代わりに、最初の自動検出サービス要求に HTTP を使用するようにリバース プロキシを構成できます。 「Planning for Mobility」トピックでは、このトピックについて詳しい情報を参照してください。
  
ディレクター プールとフロントエンド プールの証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービスの URL  <br/> |SAN=lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動検出サービスの URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
代わりに SAN= を使用できます \* 。\<sipdomain\>
  
リバース プロキシ (パブリック CA) 証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービスの URL  <br/> |SAN=lyncdiscover。\<sipdomain\>  <br/> |
   
この SAN は、リバース プロキシの SSL リスナーに割り当てられている証明書に割り当てる必要があります。
  
> [!NOTE]
> リバース プロキシ リスナーが外部 Web サービス URL の SAN を持つ。 ディレクターを展開している場合、SAN=skypewebextpool01.contoso.com や dirwebexternal.contoso.com などです (オプション)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2015 では、すべてのファイル ストレージに同じファイル共有を使用できます。 次のことを念頭に置く必要があります。
  
- ファイル共有は、直接接続ストレージ (DAS) または記憶域ネットワーク (SAN) 上に置く必要があります。これには、分散ファイル システム (DFS) と、ファイル ストア用の RAID (Redundant Array of Independent Disks) が含まれます。 DFS の詳細については、この DFS Windows Server 2012を [参照してください](https://technet.microsoft.com/library/jj127250.aspx)。
    
- ファイル共有には共有クラスターをお勧めします。 R2 を使用している場合は、R2 をクラスター化Windows Server 2012 Windows Server 2012があります。 Windows Server 2008 R2も受け入れ可能です。 最新の Windows を使用する理由 以前のバージョンには、すべての機能を有効にするための適切なアクセス許可がない場合があります。 クラスター管理者を使用してファイル共有を作成できます。クラスターで[](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster)ファイル共有を作成する方法に関する記事では、これらの詳細を確認できます。
    
> [!CAUTION] 
> ファイル共有としてのネットワーク接続ストレージ (NAS) の使用はサポートされていないので、上記のいずれかのオプションを使用してください。 
  
