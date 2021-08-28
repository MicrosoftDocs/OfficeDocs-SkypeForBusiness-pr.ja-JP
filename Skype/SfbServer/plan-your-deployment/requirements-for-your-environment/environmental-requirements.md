---
title: 2015 年の環境Skype for Business Server要件
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: '概要: 2015 年のサーバー以外の要件Skype for Business Serverします。 Active Directory、DNS、Certs、Fileshares など、展開を行う前に構成する必要があるさまざまなものがあります。'
ms.openlocfilehash: dfaf19ac3c34a13055cd496ad25d02cd4b89c783
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601332"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>2015 年の環境Skype for Business Server要件
 
**概要:** 2015 年のサーバー以外の要件Skype for Business Serverします。 Active Directory、DNS、Certs、Fileshares など、展開を行う前に構成する必要があるさまざまなものがあります。
  
2015 年の環境要件Skype for Business Server。 このトピックでは、直接サーバー関連ではないすべてをこのトピックに追加しました。そのため、クリックする必要は大きすぎです。 サーバーの前提条件を探している場合は[、Skype for Business Server 2015](server-requirements.md)ドキュメントのサーバー要件を確認できます。ネットワーク計画も個別に[](../../plan-your-deployment/network-requirements/network-requirements.md)文書化されています。 それ以外の場合は、この記事で次の情報を参照してください。
  
- [Active Directory](environmental-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](environmental-requirements.md#DNS)
  
- [証明書](environmental-requirements.md#Certs)
  
- [ファイル共有](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーとサービスの構成データの多くが Skype for Business Server 2015 のサーバーの全体管理ストアに格納されている一方で、Active Directory には以下の情報が保存されています。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||以前にサポートされているバージョンとの下位互換性を維持するための Lync Server 2013 および Lync Server 2010 の拡張機能。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (応答グループ アプリケーションや連絡先など会議アテンダント アプリケーション)。  <br/> |
||下位互換性のために公開されたデータ。  <br/> |
||サーバーの全体管理ストアのサービス コントロール ポイント (SCP)。  <br/> |
||Kerberos 認証アカウント (オプションのコンピューター オブジェクト)。  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用 OS

では、どのドメイン コントローラー OS を使用できますか? 次の一覧があります。

- WindowsServer 2019 (2015 Skype for Business Server更新プログラム 5 以降が必要)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
これで、Skype for Business Server 2015 を展開するドメインのドメイン機能レベルと、Skype for Business Server 2015 を展開するフォレストのフォレスト機能レベルは、次の 1 つである必要があります。

- WindowsServer 2019 (2015 Skype for Business Server更新プログラム 5 以降が必要)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
これらの環境で読み取り専用ドメイン コントローラーを使用できますか? 確かに、書き込み可能なドメイン コントローラーがサイトと同じサイトで使用できる限りSkype for Business Server。
  
2015 では、2015 Skype for Business Serverラベル付きドメインがサポートされていません。 その方法とは何ですか? contoso.local というラベルのルート ドメインがある場合は、問題ありません。 ローカルという名前のルート ドメインがある場合、そのドメインは機能し、その結果サポートされません。 この点についてもう少し詳しくは、この [サポート技術情報の記事で書かれています](https://support.microsoft.com/kb/300684/en-us)。
  
Skype for Business Server 2015 では、ドメイン名の変更もサポートされていません。 実際に行う必要がある場合は、Skype for Business Server 2015 をアンインストールし、ドメイン名の変更を行い、2015 年Skype for Business Server再インストールする必要があります。
  
最後に、DS 環境でロックダウンされたドメインAD処理している可能性があります。問題は問題ない場合があります。 2015 年から 2015 年を展開する方法Skype for Business Server展開ドキュメントで、その種の環境に展開する方法について説明します。
  
### <a name="ad-topologies"></a>AD トポロジ

Skype for Business Server 2015 でサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- 1 つのリソース フォレスト トポロジSkype for Business複数のフォレストと共有Exchange Online
    
- リソース フォレスト トポロジ内の複数のフォレスト (オンラインおよびSkype for Businessを使用Azure Active Directory Connect
    
環境に含めるトポロジや、2015 年 2015 年のインストール前に設定する必要があるトポロジを特定するのに役立つ図とSkype for Business Serverがあります。 簡単に行う場合は、キーも含めて次の操作を行います。
  
![これは、トポロジ図で使用されるアイコンSkype for Businessです。](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![1 つのドメインを持つ Active Directory 単一フォレストの図](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これより簡単に行えるのは、単一のドメイン フォレストです。これは一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一ツリー、および mutiple ドメインの図](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、もう一度 1 つのフォレストを示していますが、1 つ以上の子ドメインも含みます (この特定の例には 3 つがあります)。 そのため、ユーザーが作成するドメインは、2015 年に展開Skype for Business Serverドメインとは異なる場合があります。 なぜこのことを心配するのですか? フロントエンド プールを展開する場合、Skype for Business Server内のすべてのサーバーが 1 つのドメイン内にある必要がある点に注意してください。 ユニバーサル管理者グループのサポートを通Skype for Business Serverドメイン間Windows管理できます。
  
上の図に戻って、あるドメインのユーザーが、子ドメインに存在する場合でも、同じドメインまたは異なるドメインから Skype for Business Server プールにアクセスできるのを確認できます。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、および不結合の名前空間の図](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図に似たトポロジが用意されている場合がありますが、フォレストは 1 つですが、そのフォレスト内には複数のドメインが含まれるので、個別の名前空間ADがあります。 この場合、2015 年 3 つの異なるドメインのユーザーが 2015 年にアクセスする場合、この図はSkype for Business Serverです。 実線は、自分のドメイン内の Skype for Business Server プールにアクセスしている場合、破線は別のツリー内のプールに移動する場合を示します。
  
ご覧のように、同じドメイン、同じツリー、または別のツリーのユーザーは、プールに正常にアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジ図の複数のフォレスト](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 では、中央フォレスト トポロジで構成された複数のフォレストがサポートされています。 それが自分の持っているものか分からない場合、トポロジの中央フォレストは、その中のオブジェクトを使用して他のフォレストのユーザーを表し、フォレスト内のすべてのユーザーのユーザー アカウントをホストします。
  
これはどのように機能しますか? ディレクトリ同期製品 (Forefront Identity Manager、FIM など) は、存在する組織のユーザー アカウントを管理します。 アカウントがフォレストから作成または削除されると、その変更は中央フォレストの対応する連絡先に同期されます。
  
明らかに、AD インフラストラクチャがインプレイスでこのトポロジに移行している場合は簡単ではないかもしれませんが、既に存在している場合や、フォレスト インフラストラクチャを計画している場合は、この方法をお選びください。 Skype for Business Server 2015 年 2015 年の展開を 1 つのフォレスト内に集中管理することができますが、ユーザーは任意のフォレスト内の他のユーザーの存在を検索、通信、および表示できます。 すべてのユーザー連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>リソース フォレスト トポロジ内Skype for Businessフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ図内の複数のフォレスト](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソース フォレスト トポロジもサポートされています。フォレストは、2015 年から 2015 年まで、サーバー アプリケーションの実行専用Microsoft Exchange Server場所Skype for Business Serverです。 このリソース フォレストは、アクティブなユーザー オブジェクトの同期表現もホストしますが、ログオンが有効なユーザー アカウントはありません。 したがって、リソース フォレストは、ユーザー オブジェクトが存在する他のフォレストの共有サービス環境であり、リソース フォレストとのフォレスト レベルの信頼関係を持ちます。
  
このリソース Exchange Serverは、同じリソース フォレストと同じリソース フォレストSkype for Business Server別のフォレストに展開できます。
  
この種類のトポロジに Skype for Business Server 2015 を展開するには、ユーザー フォレスト内のユーザー アカウントごとに 1 つの無効なユーザー オブジェクトをリソース フォレストに作成します (Microsoft Exchange Server が環境内に既に存在する場合は、これを行う可能性があります)。 次に、ユーザー アカウントのライフ サイクルを通じてユーザー アカウントを管理するためのディレクトリ同期ツール (Forefront Identity Manager や FIM など) が必要になります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>1 つのリソース フォレスト トポロジSkype for Business複数のフォレストと共有Exchange Online
<a name="BKMK_multipleforestopology"> </a>

このトポロジは、「リソース フォレスト トポロジ内の複数のフォレストSkype for Business[似ています](environmental-requirements.md#BKMK_multipleforestopology)。
  
このトポロジでは、1 つ以上のユーザー フォレストが作成され、Skype for Business Serverリソース フォレストに展開されます。 Exchange Serverは、同じリソース フォレストまたは別のフォレストにオンプレミスで展開し、Exchange Online とのハイブリッド用に構成したり、Exchange Online によってオンプレミス アカウント専用に電子メール サービスを提供したりすることもできます。 このトポロジで使用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>リソース フォレスト トポロジ内の複数のフォレスト (オンラインおよびSkype for Businessを使用Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![2 つのAD、1 つのユーザー フォレストと 1 つのリソース フォレストを表示します。 2 つのフォレストには信頼関係があります。 これらは、Azure Microsoft 365を使用Microsoft 365またはOffice 365と同期AD Connect。 すべてのユーザーは、Skype for BusinessまたはMicrosoft 365をOffice 365。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを持つ複数のフォレストがオンプレミスにあります。 Active Directory フォレスト間には完全な信頼関係があります。 このAzure Active Directory Connectは、オンプレミスのユーザー フォレストとユーザー フォレストまたはユーザー フォレストの間でアカウントMicrosoft 365同期Office 365。
  
 また、組織はMicrosoft 365またはOffice 365し、Azure Active Directory Connectを使用して、オンプレミス[](/previous-versions/azure/azure-services/dn832695(v=azure.100))アカウントを Microsoft 365またはOffice 365。 ユーザーがオンラインで有効Skype for Businessユーザーは、Microsoft 365またはOffice 365オンラインSkype for Businessされます。 Skype for Business Serverオンプレミスでは展開されません。
  
シングル サインオン認証は、ユーザー フォレスト内にある Active Directory フェデレーション サービス ファームによって提供されます。
  
このシナリオでは、Exchange オンプレミス、Exchange Online、ハイブリッド Exchange ソリューションを展開するか、Exchangeを全く展開Exchangeサポートされています。 (この図はオンプレミスExchangeのみを示していますが、他のソリューションExchangeも完全にサポートされています)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド フォレストを使用したリソース フォレスト トポロジ内の複数Skype for Business
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1 つ以上のオンプレミス ユーザー フォレストが作成され、Skype for Business が専用のリソース フォレストに展開され、Skype for Business Online を使用したハイブリッド モード用に構成されます。 Exchange Serverは、同じリソース フォレストまたは別のフォレストにオンプレミスで展開できます。また、Exchange Online とハイブリッド用に構成Exchange Online。 または、電子メール サービスは、オンプレミス アカウントExchange Onlineによって排他的に提供される場合があります。
  
詳細については、「Configure [a multi-forest environment](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)for hybrid Skype for Business」 を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 では、次の理由により DNS が必要です。
  
- DNS を使用Skype for Business Server 2015 年に内部サーバーまたはプールを検出し、サーバー間通信を可能にします。
    
- DNS を使用すると、クライアント コンピューターは SIP トランザクションで使用Standard Editionフロントエンド プールまたはサーバーを検出できます。
    
- 会議の単純な URL を、それらの会議をホストするサーバーに関連付ける。
    
- DNS を使用すると、外部ユーザーとクライアント コンピューターは、インスタント メッセージング (IM) または会議のためにエッジ サーバーまたは HTTP リバース プロキシに接続できます。
    
- これにより、ログインしていない統合通信 (UC) デバイスが、Device Update Web サービスを実行しているフロントエンド プールまたは Standard Edition サーバーを検出して、更新プログラムを取得してログを送信できます。
    
- DNS を使用すると、モバイル クライアントは、ユーザーがデバイス設定で URL を手動で入力する必要なしに、Web サービス リソースを自動的に検出できます。
    
- また、DNS 負荷分散で使用されます。
    
2015 年は国際化ドメインSkype for Business Server (IDN) をサポートしない点に注意することが重要です。
  
また、DNS の名前は、2015 年に使用されているサーバーで構成されたコンピューター名と同一Skype for Business Serverです。 具体的には、環境内にショートネームを含めず、トポロジ ビルダー用の FQDN が必要です。
  
これは、既にドメインに参加している任意のコンピューターに対して論理的なようですが、ドメインに参加していないエッジ サーバーがある場合は、既定の短い名前で、ドメイン サフィックスはありません。 DNS またはエッジ サーバー、または 2015 年 2015 年のサーバーまたはプールSkype for Business Server、そうでなくしてください。
  
また、Unicode 文字やアンダースコアは使用しません。 標準文字 (A-Z、a-z、0-9、ハイフン) は、外部 DNS および公的な証明書機関でサポートされる文字です (証明書の SN に FQDN を割り当てる必要があります。忘れないでください)、これを念頭に置いて名前を付けておいた場合は、多くの悲しみを忘れないでください。
  
ネットワークの DNS 要件の詳細については、「計画」のドキュメントの「 [ネットワーク](../../plan-your-deployment/network-requirements/network-requirements.md) 」セクションを参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開する前に実行できる最も重要な点の 1 つは、証明書の順序を確認する方法です。 Skype for Business Server 2015 では、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) が必要です。 基本的に、標準化された方法で安全に通信するために、Skype for Business Server認証局 (CA) によって発行された証明書を使用します。
  
2015 年に証明書を使用Skype for Business Server次に示します。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Web アクセスOutlook (OWA)
    
したがって、証明書の計画は必ず行う必要があります。 次に、証明書を要求する際に注意する必要があるいくつかの一覧を見てみます。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書は、オペレーティング システムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Skype for Business Server 2015 は、SHA-1 および SHA-2 スイートのダイジェスト サイズ (224、256、384、512 ビット) をサポートし、オペレーティング システム要件を満たすか、または超えています。
    
- 自動登録は、2015 年に実行されている内部Skype for Business Serverサポートされています。
    
- 自動登録は、2015 エッジ サーバー Skype for Business Serverサポートされていません。
    
- Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。
    
> [!NOTE]
> KB922706 では、Windows Server 2003 証明書サービス Web 登録に対する Web 証明書の登録に関する問題の解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して Windows Server 2003 CA から証明書を要求することはできません。 
  
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされていないため、ログインおよび通話転送の問題などのエラーにつながる可能性があります。 

> [!NOTE]
> Skype for Business Server 2015 では、CNG 証明書はサポートされていません。
  
- 1024、2048、および 4096 の暗号化キーの長さがサポートされています。 キーの長さは 2048 以上をお勧めします。
    
- 既定のダイジェスト (ハッシュ署名) アルゴリズムは RSA です。 またECDH_P256、ECDH_P384、ECDH_P521アルゴリズムもサポートされています。
    
そのため、CA から証明書を要求するさまざまな快適さレベルについて考えるべきことはたくさんあるのです。 計画を可能な限り簡単に行う方法については、以下のガイダンスをご覧ください。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバーの証明書

ほとんどの内部サーバーに対して証明書が必要になります。多くの場合、内部 CA (ドメイン内にある CA) から証明書を取得します。 必要に応じて、外部 CA (インターネット上にある証明書) からこれらの証明書を要求できます。 どのパブリック CA にアクセスする必要があるのか疑問に思う場合は、ユニファイド コミュニケーション証明書パートナーの一覧 [を確認](../../../SfbPartnerCertification/certification/services-ssl.md) できます。
  
また、Skype for Business Server 2015 年 2015 年に他のアプリケーションやサーバー (Microsoft Exchange Server など) と通信する場合にも、証明書が必要Microsoft Exchange Server。 これは明らかに、これらの他のアプリやサーバーがサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2015 および他の Microsoft 製品は、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 この記事に興味がある場合は、OAuth と 2015 年のSkype for Business Serverがあります。
  
Skype for Business Server 2015 には、SHA-256 暗号化ハッシュ関数を使用して署名された (不要な) 証明書のサポートも含まれています。 SHA-256 を使用して外部アクセスをサポートするには、SHA-256 を使用してパブリック CA によって外部証明書を発行する必要があります。
  
わかりやすくするために、Standard Edition サーバー、フロントエンド プール、その他の役割の証明書要件を次の表に入れ、架空の contoso.com を例に使用します (おそらく、環境に別の機能を使用している可能性があります)。 これらはすべて標準の Web サーバー証明書で、プライベート キーはエクスポートできません。 次の点に注意する必要があります。
  
- 証明書ウィザードを使用して証明書を要求すると、サーバー拡張キー使用法 (EKU) が自動的に構成されます。
    
- 各証明書の表示名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクト代替名 (SAN) に追加する必要があります。
    
サーバーのStandard Edition:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |Standard Edition サーバーに関しては、サーバー FQDN とプール FQDN は同じです。  <br/> ウィザードは、セットアップ中に指定した SIP ドメインを検出し、サブジェクトの代替名として自動的に追加します。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じです)  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=se01.contoso.com;SAN= \* .contoso.com  <br/> |トポロジ ビルダーで内部 Web FQDN を上書きできない。  <br/> 複数の Meet 単純な URL がある場合は、すべての URL を SAN として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルインの簡単な URL  <br/> • SIP ドメインごとの単純な URL を満たす  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |複数の Meet 単純な URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンド プール内のフロントエンド サーバー Enterprise Edition証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN とサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証にも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じではない)  <br/> • サーバー FQDN  <br/> • Skype for Business FQDN  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN= \* .contoso.com  <br/> |複数の Meet 単純な URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN= \* .contoso.com  <br/> |複数の Meet 単純な URL がある場合は、すべての URL をサブジェクトの代替名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |ディレクター プール  <br/> |ディレクター の FQDN、ディレクター プールの FQDN。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS 照合が必要な場合は、sip.sipdomain (ユーザーが持つ SIP ドメインごとに) のエントリも必要です。  <br/> |pool.contoso.com;SAN=dir01.contoso.com  <br/> このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 Web FQDN (サーバーの FQDN と同じです)  <br/> • サーバー FQDN  <br/> • Skype for Business FQDN  <br/> AND  <br/> • 単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> • 管理者の簡単な URL  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 Web FQDN  <br/> AND  <br/> • SIP ドメインごとの単純な URL を満たす  <br/> • ダイヤルインの簡単な URL  <br/> または  <br/> • 単純な URL のワイルドカード エントリ  <br/> |ディレクターの外部 Web FQDN は、フロント エンド プールまたはフロント エンド サーバーとは異なる必要があります。  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
スタンドアロン仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net。SAN=medsvr-pool.contoso.net。SAN=medsvr01.contoso.net  <br/> |
   
存続可能ブランチ アプライアンスの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |アプライアンスの FQDN  <br/> |SIP。\<sipdomain\> (SIP ドメインごとに必要なエントリは 1 つのみです)  <br/> |SN=sba01.contoso.net;SAN=sip.contoso.com;SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>常設チャット サーバーの証明書

常設チャット サーバーをインストールする場合は、Skype for Business Server 2015 内部サーバーで使用されているのと同じ CA によって発行された証明書が必要になります。 これは、ファイルの永続的なチャット Web サービスを実行しているサーバーごとに実行する必要がありますアップロード/ダウンロードします。 常設チャット のインストールを開始する前に、必要な証明書を持ち、CA が外部の場合はさらに多くの証明書を使用することを強くお勧めします (これらの場合、発行に少し時間がかかる場合があります)。
  
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス用の証明書 (Edge)

Skype for Business Server 2015 では、アクセスおよびWeb 会議エッジの外部インターフェイスに 1 つのパブリック証明書と、エッジ サーバー経由で提供される音声ビデオ認証サービスの使用がサポートされています。 エッジ内部インターフェイスは、通常、内部 CA によって発行されたプライベート証明書を使用しますが、必要に応じて、信頼できる CA からのパブリック証明書も使用できます。
  
リバース プロキシ (RP) もパブリック証明書を使用し、RP からクライアントへの通信、および HTTP (またはより正確には HTTP 上の TLS) を使用して RP から内部サーバーへの通信を暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティの証明書

モビリティを展開し、モバイル クライアントの自動検出をサポートしている場合は、モバイル クライアントからの安全な接続をサポートするために、証明書に追加のサブジェクト代替名エントリを含める必要があります。
  
どの certs? 証明書の自動検出には、次の SAN 名が必要です。
  
- ディレクター プール
    
- フロント エンド プール
    
- リバース プロキシ
    
以下の各表に詳細を示します。
  
これで、少し事前計画が適していますが、モビリティの展開を意図せずに Skype for Business Server 2015 を展開した場合、環境に証明書が既に存在する場合は、この手順が実行されます。 通常、内部 CA を介して再発行するのは簡単ですが、パブリック CA からのパブリック証明書では、もう少しコストがかかる場合があります。
  
それが見ている場合で、SIP ドメインが多い場合 (SANS を追加するコストが高くなります)、HTTPS を使用する代わりに、最初の自動検出サービス要求に HTTP を使用するようにリバース プロキシを構成できます (これは既定の構成です)。 モビリティの計画に関するトピックでは、この詳細情報を参照してください。
  
ディレクター プールとフロントエンド プール証明書の要件:
  
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
> リバース プロキシ リスナーは、外部 Web サービス URL の SANS を持つ必要があります。 ディレクターを展開した場合、SAN=skypewebextpool01.contoso.com と dirwebexternal.contoso.com が使用されます (これはオプションです)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2015 では、すべてのファイル ストレージに同じファイル共有を使用できます。 次のことを念頭に置く必要があります。
  
- ファイル共有は、直接接続ストレージ (DAS) または記憶域ネットワーク (SAN) 上にある必要があります。これには、分散ファイル システム (DFS) と、ファイル ストア用の独立ディスク (RAID) の冗長配列が含まれます。 DFS for Windows Server 2012については、この[DFS ページを参照してください](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))。
    
- ファイル共有の共有クラスターをお勧めします。 1 つを使用している場合は、R2 Windows Server 2012クラスター Windows Server 2012必要があります。 Windowsサーバー 2008 R2 も使用できます。 最新のWindows? 以前のバージョンでは、すべての機能を有効にする適切なアクセス許可がない場合があります。 クラスター管理者を使用してファイル共有を作成 [できます。この](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) 「クラスターでファイル共有を作成する方法」の記事は、これらの詳細に役立ちます。
    
> [!CAUTION] 
> ネットワーク接続ストレージ (NAS) をファイル共有として使用する機能はサポートされていないので、上記のいずれかのオプションを使用してください。 
