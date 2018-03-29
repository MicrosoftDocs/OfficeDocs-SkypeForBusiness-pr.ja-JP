---
title: Skype for Business Server 2015 の環境要件
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: '概要: ビジネス サーバー 2015 の Skype の非サーバー要件を構成します。 これらに該当するのは、Active Directory、DNS、証明書、ファイル共有など、展開を実行する前に構成しようとするさまざまな事項です。'
ms.openlocfilehash: 0d71140678654442caef112f6132695c76d3ea6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の環境要件
 
**の概要:**Skype ビジネス サーバー 2015 の以外のサーバーの要件を構成します。 これらに該当するのは、Active Directory、DNS、証明書、ファイル共有など、展開を実行する前に構成しようとするさまざまな事項です。
  
ビジネス サーバー 2015 の Skype の環境の要件とは何ですか。 ご用意しましたすべての直接の周りをクリックすると実行する必要はありませんので、このトピックに関連するサーバーではありません。 探しているサーバーの前提条件、[ビジネス サーバー 2015 の Skype のサーバー要件](server-requirements.md)のドキュメントをチェック_アウトすることができる場合[ネットワークの計画](../../plan-your-deployment/network-requirements/network-requirements.md)も記載されて個別にします。 それ以外の場合、これは、どのような我々 には、この資料です。
  
- [Active Directory](environmental-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](environmental-requirements.md#DNS)
  
- [証明書](environmental-requirements.md#Certs)
  
- [ファイル共有](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

大量のサーバーおよびサービスの構成データをビジネス サーバー 2015 の中央管理ストアの Skype では、中には、Active Directory にまだ保存されているものがあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||前との下位互換性を維持するために Lync Server 2013 および Lync Server 2010 の拡張機能でサポートされているバージョンです。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||(応答グループ アプリケーションや会議アテンダント アプリケーション) などのアプリケーションの連絡先オブジェクトです。  <br/> |
||下位互換性について公開されたデータ。  <br/> |
||サービス コントロールでは、中央管理ストアに (SCP) をポイントします。  <br/> |
||Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)。  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用の OS

どのドメイン コントローラー用 OS を使用できるかについては、以下の一覧を参照してください。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
ここで、Skype を配置するには、ビジネスのサーバー 2015 の任意のドメインのドメインの機能レベルとフォレストの機能レベルには、ビジネスのサーバー 2015 の Skype を配置する任意のフォレストは、次のいずれかにする必要が。
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
これらの環境では、書き込み可能なドメイン コントローラーを使用できれば、読み取り専用ドメイン コントローラーも使用できます。
  
Skype ビジネス サーバー 2015 の単一ラベルのドメインをサポートしていないことを確認するのには重要です。 単一ラベルのドメインがどのようなものかを把握しておいてください。 Contoso.local というラベルの付いたルート ドメインがあれば、十分にそうです。 ルート ドメイン ローカルという名前だけがあれば、作業をすることはしませんし、結果としてサポートされていません。 もう少しこれについて書かれています[このサポート技術情報の記事で](https://support.microsoft.com/kb/300684/en-us).
  
ビジネス サーバー 2015 の Skype は、ドメイン名の変更もサポートしていません。 いる場合実際が必要があるビジネス サーバー 2015 年の Skype をアンインストールするのにはドメインの名前変更の操作を行い、ビジネス サーバー 2015 の Skype を再インストールします。
  
最後に、ロックされた AD DS 環境では、ドメインを扱うことがあり、大丈夫です。 ビジネス サーバー 2015 の展開のドキュメント内の環境のように Skype を導入する方法の詳細があります。
  
### <a name="ad-topologies"></a>Active Directory トポロジ

Skype ビジネス サーバー 2015 のサポートされているトポロジには次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
    
図と、環境、またはビジネス サーバー 2015 の Skype をインストールする前に設定する必要がありますが、どのようなトポロジを決定するための説明があります。 保つには、単純なキーも含めています。
  
![Skype for Business トポロジ図に使用される主なアイコン](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![ドメインが 1 つである Active Directory の単一フォレストの図](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これよりも簡単に取得する、単一ドメインのフォレストが、これは、一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、複数のドメインがある図](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、単一のフォレストを示していますが、1 つまたは複数の子ドメインにも (ある特定の例ではこの 3 つ) があります。 ビジネス サーバー 2015 を展開するため、ユーザーがで作成したドメインが Skype のドメインとは異なる可能性があります。 これに関する心配は無用でしょうか。 Skype のビジネス サーバーのフロント エンド プールを展開する際の点に注意することが重要、そのプール内のすべてのサーバーが 1 つのドメインにインストールする必要があります。 Windows 管理者のユニバーサル グループのビジネス サーバーのサポートのための Skype 経由での管理のドメインを越えたことができます。
  
上の図に、1 つのドメインからのユーザーがビジネス サーバーのプール同じドメインからまたは別のドメインからの Skype にアクセスできない場合でも、子ドメインでは、それらのユーザーを確認できます。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、不整合の名前空間がある図](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
ところトポロジがある、この図のような 1 つのフォレストがある可能性がありますが、別の AD の名前空間を持つ複数のドメインは、そのフォレスト内にあります。 場合は、この図の適切な図では、ビジネス サーバー 2015 の Skype にアクセスする 3 つの異なるドメインにユーザーがあります。 純色の線を示す破線は、しようとしているプールを別のツリー全体を示すときにビジネス サーバー プールを自身のドメイン内の Skype にアクセスしています。
  
図のように、同一のドメイン、同一のツリーだけでなく、異なるツリーのユーザーも正常にプールにアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジの複数のフォレストの図](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
ビジネス サーバー 2015 の Skype では、中央フォレスト トポロジで構成されている複数のフォレストをサポートします。 何があることを確認していない場合は、中央フォレスト トポロジでは、オブジェクトを使用することで、他のフォレスト、およびフォレスト内のユーザーのユーザー アカウントをホストのユーザーを表します。
  
これがどのように動作しているでしょうか。 Forefront ユーザー マネージャー、または FIM) などのディレクトリ同期製品は、全体の存在で、組織のユーザーのアカウントを管理します。 アカウントが作成または削除されたとき、フォレストから中央フォレスト内の対応する連絡先に変更が同期されること。
  
明らかに、AD インフラストラクチャでは、インプレースこのトポロジに移行できない場合があります、簡単ですが、されて場合、または計画が、フォレストのインフラストラクチャをこの、適切な選択ができます。 ユーザーは、検索、通信、および任意のフォレスト内の他のユーザーのプレゼンスを表示中に、1 つのフォレスト内のサーバー 2015 のビジネス展開に、Skype を集中管理できます。 すべてのユーザーの連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ内に複数のフォレストがある図](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソース フォレストのトポロジもサポートされています。フォレストは Microsoft Exchange Server およびビジネス サーバー 2015 の Skype のように、サーバー アプリケーションを実行するのには専用の場所をお勧めします。 このリソース フォレストでは、アクティブなユーザー オブジェクトの同期表現ですがないログオンが有効なユーザー アカウントもホストします。 リソース フォレストとは、共有サービス環境の他のフォレストのユーザー オブジェクトが存在し、リソース フォレストのフォレスト レベルの信頼関係があるのです。
  
Skype ビジネス サーバーと同じリソース フォレストまたは別のフォレストの Exchange Server を展開することに注意してください。
  
ユーザー フォレスト内のユーザー アカウントごとに、リソース フォレストで 1 つの無効なユーザー オブジェクトを作成するこの種類のトポロジでのビジネス サーバー 2015 の Skype を展開する (Microsoft Exchange Server が既に環境にいる場合は、これが自動的に行われます)。 (Forefront ユーザー マネージャーでは、FIM など) のディレクトリ同期ツールのライフ サイクルを通じてのユーザー アカウントを管理する必要があります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは「[Skype for Business リソース フォレスト トポロジの複数フォレスト](environmental-requirements.md#BKMK_multipleforestopology)」で説明されるトポロジと同様のものです。
  
このトポロジでは、1 つまたは複数のユーザーのフォレストがあるし、Skype ビジネス サーバーの専用リソース フォレストに展開します。 Exchange Server を選択し、展開したオンプレミス リソース フォレストを同じまたは別のフォレストでは、Exchange online では、ハイブリッド用に構成されたまたは設置型のアカウントの Exchange のオンラインでのみ電子メール サービスを提供することがあります。 このトポロジの図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つの AD フォレスト (ユーザー フォレストとリソース フォレスト) があります。これらの 2 つのフォレストの間には、信頼関係が確立されています。これらの 2 つのフォレストは、Azure AD Connect を使用して Office 365 と同期されます。すべてのユーザーは、Office 365 経由で Skype for Business を利用できます。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを使用するオンプレミスの複数のフォレストが存在し、Active Directory フォレスト間には完全な信頼関係がある場合を考えます。オンプレミス ユーザー フォレストと Office 365 との間のアカウントを同期するために、Azure Active Directory Connect ツールが使用されます。
  
 組織も、Office 365 があり、 [Azure Active Directory の接続](https://go.microsoft.com/fwlink/p/?LinkId=614836)を使用して、オンプレミス アカウントを Office 365 に同期します。 Office 365 と Skype では、オンライン ビジネスのビジネス用の Skype は、有効になっているユーザーが有効です。 ビジネス サーバー用の Skype は、オンプレミスで導入ではありません。
  
シングル サインオン認証は、ユーザーのフォレストにある、Active Directory フェデレーション サービス ファームによって提供されます。
  
このシナリオでは Exchange の設置型、Exchange Online では、ハイブリッドの Exchange ソリューションを展開するか、しないに展開される Exchange サポートします。 (図のみ交換設置を示していますが、他の Exchange ソリューションが完全にサポートされている)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1 つを使用する必要がある以上、オンプレミス ユーザーのフォレスト、ビジネスの Skype 専用のリソース フォレストに展開し、ビジネス オンラインの Skype でハイブリッド モードの構成 Exchange Server は、展開したオンプレミス リソース フォレストを同じまたは別のフォレストし、Exchange online のハイブリッド用に構成することがあります。 または、電子メール サービスを Exchange Online でのみ設置型のアカウントの提供できます。
  
詳細については、[ハイブリッド ビジネスの Skype の複数のフォレスト環境の構成](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

ビジネス サーバー 2015 の Skype では、次の理由により、DNS が必要です。
  
- DNS は、サーバーからサーバーへの通信を許可する内部サーバーまたはプールを検出するのには、ビジネス サーバー 2015 の Skype を使用できます。
    
- DNS では、クライアント マシンのフロント エンド プールまたは Standard Edition サーバーの SIP トランザクションの使用を検出します。
    
- 会議用の簡易 URL と、これらの会議をホストするサーバーが関連付けられます。
    
- DNS は、エッジ サーバー、HTTP 用リバース プロキシ、インスタント メッセージング (IM) または会議に接続するには、外部のユーザーやクライアント コンピューターです。
    
- 統合コミュニケーション (UC) を使用してフロント エンド プールまたは Standard Edition サーバーの更新プログラムを取得し、ログを送信するデバイス更新 web サービスを実行しているデバイスにログインしていないことを検出します。
    
- DNS を使用すると、モバイル クライアントでは、デバイス設定で URL を手動入力しなくても Web サービス リソースを自動的に検出できます。
    
- また、DNS は DNS ロード バランシングで使用されます。
    
Skype ビジネス サーバー 2015 の国際化ドメイン名 (Idn) をサポートしていないことに注意する必要があります。
  
覚えておくことは非常に重要と DNS 内の任意の名前がビジネス サーバー 2015 の Skype で使用されている任意のサーバーで構成されているコンピューター名と同一であること。 具体的には、環境内の任意の短い名前を持つことはできませんし、トポロジ ビルダーの Fqdn を指定する必要があります。
  
これは、ドメインに既に参加している任意のコンピューターの論理が、短い形式の名前、ドメイン サフィックスなしの既定値を必要がある場合は、ドメインに参加していないエッジ サーバーがある場合は、ように思われます。 しない場合は、dns、またはエッジ サーバー、またはビジネス サーバー 2015 サーバーまたはプール、さらに言えば、Skype では、あることを確認します。
  
Unicode 文字またはアンダー スコアを使用しない確実です。 標準的な文字が文字 (A-Z、a-z、0-9、およびハイフン) は、外部 DNS およびパブリック証明機関によってサポートされるしようとしているもの (Fqdn を証明書の SN に割り当てする必要があることを忘れないでください) のでしたが予備の自分でたくさんの場合、名前をこのことに注意します。
  
ネットワークの DNS 要件に関するその他の情報については、「計画」ドキュメントの「[Networking](../../plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開の前の最も重要な作業の 1 つは、証明書を用意することです。 ビジネス サーバー 2015 の Skype では、トランスポートの公開キー基盤 (PKI) が必要なレイヤーのセキュリティ (TLS) と相互トランスポート層セキュリティ (MTLS) 接続します。 基本的には、標準化された方法で安全に通信をする Skype のビジネス サーバーは証明機関 (Ca) によって発行された証明書を使用します。
  
ビジネス サーバー 2015 の Skype 用の証明書を使用しているものがあります。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Outlook Web Access (OWA) を話す
    
必要がありますが、証明書の計画の。 ここで、証明書を要求するときに留意すべき事項のいくつかのリストを見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書が、オペレーティング システムでサポートされている署名アルゴリズムによって署名されている必要がある。 ビジネス サーバー 2015 の Skype は、SHA-1 をサポートし、ダイジェスト群の SHA 2 (224 256、384、512 ビット) のサイズとを満たしているか、オペレーティング システムの要件を超えています。
    
- ビジネス サーバー 2015 の Skype を実行している内部のサーバーの自動登録がサポートされています。
    
- ビジネス 2015 エッジ サーバー用の Skype、自動登録がサポートされていません。
    
- Windows Server 2003 CA に web ベースの証明書の要求を送信するときは、SP2 または Windows XP、Windows Server 2003 を実行するコンピューターから送信する必要があります。
    
> [!NOTE]
> KB922706 は、Windows Server 2003 証明書サービスの Web 登録について Web 証明書の登録に関わる問題解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して、Windows Server 2003 CA から証明書を要求できるようにはなりません。 
  
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされておらず、数ある問題の中でも、ログイン時のエラーや着信転送時の問題につながる可能性があります。 
  
- 暗証キーの長さとして 1024、2048、4096 がサポートされます。2048 以上のキーの長さはお勧めしません。
    
- 既定のダイジェストまたはハッシュ アルゴリズムは RSA です。ECDH_P256、ECDH_P384、ECDH_P521 のハッシュ アルゴリズムもサポートされます。
    
考えて、多くは、間違いなく、さまざまな CA から証明書を要求すると快適さのレベル。 紹介の下にいくつか詳しく計画をできるだけ楽に作成します。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバー用の証明書

証明書を内部のサーバーのほとんどする必要があり、ほとんどの場合、(1 つである、ドメイン内にある) 内部の CA から入手できますがします。 必要に応じて、外部の CA (インターネット上に存在する CA) から証明書を要求できます。 参考までにどのような公共の CA の場合に進んでください、[ユニファイド コミュニケーション パートナーを証明書](https://support.microsoft.com/kb/929395/en-us)のリストをチェックすることができます。
  
しようとしているビジネス サーバー 2015 の Skype は、他のアプリケーションや Microsoft Exchange Server などのサーバーと通信するときに証明書を必要があります。 この証明書は当然、サポートされている方法でこれらの他のアプリケーションやサーバーが使用できる証明書である必要があります。 Skype ビジネス サーバー 2015 およびその他のマイクロソフト製品には、サーバーからサーバーへの認証と承認のためオープン認証 (OAuth) プロトコルをサポートします。 これに興味があるなら、ビジネス サーバー 2015 の OAuth と Skype の他の計画の資料があります。
  
ビジネス サーバー 2015 の Skype を使用せず) のサポートも含まれます、sha-256 暗号ハッシュ関数を使用して署名された証明書です。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。
  
簡単なものに抑えるをご用意しました Standard Edition サーバー、フロント エンド プール、およびその他のロールでは、証明書の要件を次のテーブルでは、(おそらく使用するものの例で使用されている架空の contoso.com の他の環境)。 これらは、すべて標準的な web サーバー証明書、秘密キーをエクスポートできないのです。 いくつか追加の点に注意してください。
  
- サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名が DNS に sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は証明書のサブジェクト代替名 (SAN) を追加する必要が。 あります
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**代わりのサブジェクト名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=se01.contoso.com です。SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |Standard Edition サーバーの Standard Edition サーバーにサーバーの FQDN とは、プールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN は、サーバーの FQDN と同じ)  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=se01.contoso.com です。SAN=se01.contoso.com です。SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com です。SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com です。SAN=se01.contoso.com です。SAN =\*. contoso.com  <br/> |内部 web トポロジ ビルダー内の FQDN を無効にすることはできません。  <br/> 会議の簡易 URL が複数存在する場合、それらすべてを SAN として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> ・ ダイヤルで簡単な URL  <br/> • SIP ドメインごと対応の簡単な Url。  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=se01.contoso.com です。SAN=webcon01.contoso.com です。SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=se01.contoso.com です。SAN=webcon01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含むようにできました。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
フロント エンド プール内のフロント エンド サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**代わりのサブジェクト名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=eepool.contoso.com です。SAN=eepool.contoso.com です。SAN=ee01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN (これは、サーバーの FQDN と同じ)  <br/> • サーバーの FQDN  <br/> • Skype ビジネス プールの FQDN  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=ee01.contoso.com です。SAN=ee01.contoso.com です。SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com です。SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com です。SAN=ee01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含むようにできました。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=ee01.contoso.com です。SAN=webcon01.contoso.com です。SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=ee01.contoso.com です。SAN=webcon01.contoso.com です。SAN =\*. contoso.com  <br/> |対応の複数の簡単な Url の場合は、サブジェクト代替名としては、それらのすべてを含むようにできました。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**代わりのサブジェクト名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |ディレクター プール  <br/> |ディレクター、ディレクター プールの FQDN の FQDN です。  <br/> このプールは、クライアントの自動ログオン サーバー、グループ ポリシーで厳密な DNS マッチングのために必要な場合は、(各 SIP ドメイン) の sip.sipdomain のエントリ必要もあります。  <br/> |pool.contoso.com です。SAN=dir01.contoso.com  <br/> このダイレクタ ・ プールは、クライアントの自動ログオン サーバーと、グループ ポリシーで厳密な DNS マッチングが必要なする必要も SAN=sip.contoso.com。SAN=sip.fabrikam.com  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 内部 web FQDN は、サーバーの FQDN と同じ)  <br/> • サーバーの FQDN  <br/> • Skype ビジネス プールの FQDN  <br/> および  <br/> • 対応の簡単な Url  <br/> ・ ダイヤルで簡単な URL  <br/> • 管理の簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |SN=dir01.contoso.com です。SAN=dir01.contoso.com です。SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com です。SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com です。SAN の SAN=dir01.contoso.com =\*. contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> • 外部 web FQDN  <br/> および  <br/> • SIP ドメインごと対応の簡単な Url。  <br/> ・ ダイヤルで簡単な URL  <br/> または  <br/> • 簡単な Url のワイルドカード エントリ  <br/> |ディレクターの外部 web FQDN は、フロント エンド プールまたはフロント エンド サーバーとは異なるである必要があります。  <br/> SN=dir01.contoso.com です。SAN=directorwebcon01.contoso.com SAN=meet.contoso.com です。SAN=meet.fabrikam.com です。SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN=dir01.contoso.com です。SAN の SAN=directorwebcon01.contoso.com =\*. contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**代わりのサブジェクト名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN = medsvr-pool.contoso.net です。SAN = medsvr-pool.contoso.net です。SAN=medsvr01.contoso .net  <br/> |
   
リカバリ性に優れたブランチ アプライアンス用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**代わりのサブジェクト名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |アプライアンスの FQDN  <br/> |SIP。\<sipdomain\> (SIP ドメインごとに 1 つだけのエントリが必要)  <br/> |SN=sba01.contoso .net です。SAN=sip.contoso.com です。SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>常設チャット サーバー用の証明書

永続的なチャット サーバーをインストールするときにしようとしている内部サーバーのビジネス サーバー 2015、Skype で使用されるものと同一の証明機関によって発行された証明書が必要です。 永続的なチャット Web サービスのファイルのアップロード/ダウンロードを実行する各サーバーで実行する必要があります。 必要な証明書がある場合、CA は、外部との永続的なチャットのインストールを開始する前に強くお勧めはなおさら (次のような時間をかけて少し発行)。
  
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス (エッジ) 用の証明書

ビジネス サーバー 2015 の Skype は、アクセスおよび web 会議エッジ外部インターフェイスに加えて、A の**1 つのパブリック証明書**の使用をサポートしている/V 認証サービスは、エッジ サーバー経由で提供されています。 エッジの内部インターフェイスは、通常、内部 CA によって発行されるプライベート証明書を使用する場合、使用することがパブリック証明書この同様に、信頼された CA からである場合。
  
またリバース プロキシ (RP) でも、パブリック証明書を使用して、RP からクライアントへの通信と RP から内部サーバーへの通信を、HTTP (厳密には TLS over HTTP) を使用して暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

モビリティを展開しているモバイル クライアントの自動検出をサポートしている場合は、しようとしているモバイル クライアントからセキュリティで保護された接続をサポートする証明書のいくつかの追加のサブジェクト代替名エントリを含める必要があります。
  
以下の証明書に、自動検出に対応する SAN 名が必要です。
  
- ディレクター プール
    
- フロントエンド プール
    
- リバース プロキシ
    
以下の各表で、仕様を示します。
  
ようになりましたが、これは、少しの事前計画が良いですも展開した Skype ビジネス サーバー 2015 のモビリティを展開する必要のない付属線を環境内で証明書が既にある場合。 通常、内部 CA を介した証明書の再発行は簡単ですが、パブリック CA のパブリック証明書を使用する場合は、多少コストが上がる可能性があります。
  
(これは既定では HTTPS を使用する代わりに、最初の自動検出サービス要求の HTTP を使用するのにはリバース プロキシを構成するには何を探して、これは、(これは加えることがより高価な SAN) の SIP ドメインの多くがある場合は、構成)。 詳細については、「モビリティの計画」を参照してください。
  
ディレクター プールとフロント エンド プールは、要件を証明書します。
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN lyncdiscoverinternal を = します。\<sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN lyncdiscover を = します。\<sipdomain\>  <br/> |
   
または SAN を使用することができます =\*。\<sipdomain\>
  
リバース プロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN lyncdiscover を = します。\<sipdomain\>  <br/> |
   
この SAN を、リバース プロキシ上の SSL リスナーに割り当てられる証明書に割り当てる必要があります。
  
> [!NOTE]
> 外部 Web サービス個の URL 用に San をリバース プロキシのリスナーのこと。 あります SAN=skypewebextpool01.contoso.com と dirwebexternal.contoso.com、(これはオプションです)、ディレクターを展開した場合です。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

ビジネス サーバー 2015 の Skype は、すべてのファイル ・ ストレージを同じファイル共有を使用すること。 以下の点を考慮する必要があります。
  
- ファイル共有は、直接取り付け記憶域 (DAS) と記憶域ネットワーク (SAN) のいずれかに配置する必要があり、またファイル共有には、分散ファイル システム (DFS) だけでなくファイル ストア用の RAID (Redundant Array of Independent Disks) も含まれます。 さらに、Windows Server 2012 の DFS の詳細、[この DFS のページ](https://technet.microsoft.com/en-us/library/jj127250.aspx)をご覧ください。
    
- 共有クラスター ファイル共有に対応することをお勧めします。 いずれかを使用している場合は、Windows Server 2012 または Windows Server 2012 R2 をクラスターする必要があります。 Windows Server 2008 R2 はも許容されます。 なぜ最新の Windows でしょうか。 以前のバージョンは、すべての機能を有効にする適切なアクセス許可をいない可能性があります。 クラスター アドミニストレーターを使用するには、ファイル共有を作成して、この KB[のクラスターを作成する](https://support.microsoft.com/kb/284838)資料に役立つ詳細を記載しました。
    
> [!CAUTION]
> ファイル共有にネットワーク接続ストレージ (NAS) は使用できません。ファイル共有には、上記のいずれかの選択肢を利用してください。 
  

