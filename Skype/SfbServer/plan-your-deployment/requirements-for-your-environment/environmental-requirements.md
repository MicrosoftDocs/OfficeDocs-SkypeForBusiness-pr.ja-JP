---
title: Skype for Business Server 2015 の環境要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server 2015 のサーバー以外の要件を構成します。 展開の前に構成する必要があるさまざまな事項があります (Active Directory、DNS、証明書、ファイルの Hare など)。'
ms.openlocfilehash: d552c0c2c6b9f129b6dcf08e927634c6e3bdde6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220877"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 の環境要件
 
**概要:** Skype for Business Server 2015 のサーバー以外の要件を構成します。 展開の前に構成する必要があるさまざまな事項があります (Active Directory、DNS、証明書、ファイルの Hare など)。
  
Skype for Business Server 2015 の環境要件について ここでは、直接サーバーではないすべてのものをこのトピックに関連付けているので、クリックするだけで十分です。 サーバーの前提条件については、「 [Skype For Business server 2015 doc のサーバー要件](server-requirements.md)」を参照してください。[ネットワークの計画](../../plan-your-deployment/network-requirements/network-requirements.md)も、個別に文書化されています。 それ以外の場合、この記事では次のようになります。
  
- [Active Directory](environmental-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](environmental-requirements.md#DNS)
  
- [証明書](environmental-requirements.md#Certs)
  
- [ファイル共有](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーおよびサービスの構成データの多くは Skype for Business Server 2015 の中央管理ストアに格納されていますが、Active Directory に保存されているものもあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||以前サポートされていたバージョンとの下位互換性を維持するための Lync Server 2013 および Lync Server 2010 の拡張機能。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (応答グループアプリケーションや会議アテンダントアプリケーションなど)。  <br/> |
||下位互換性のために公開されたデータ。  <br/> |
||中央管理ストアのサービスコントロールポイント (SCP)。  <br/> |
||Kerberos 認証アカウント (オプションのコンピューターオブジェクト)。  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメインコントローラーの OS

そのため、どのドメインコントローラー OS を使用できますか。 次のリストがあります。

- Windows Server 2019 (Skype for Business Server 2015 累積的な更新プログラム5以降が必要です)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
今では、Skype for business Server 2015 を展開するドメインのドメイン機能レベルと、Skype for Business Server 2015 を展開するフォレストの機能レベルは、次のいずれかである必要があります。

- Windows Server 2019 (Skype for Business Server 2015 累積的な更新プログラム5以降が必要です)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
これらの環境には読み取り専用ドメインコントローラーがありますか。 同様に、Skype for Business Server と同じサイトで使用できる書き込み可能なドメインコントローラーがある場合は、そのことを確認してください。
  
ここでは、Skype for Business Server 2015 では、単一のラベルが付いたドメインをサポートしていないことを理解しておくことが重要です。 どのようなものですか。 Contoso というラベルが付けられたルートドメインがある場合は、問題なく動作します。 ローカルという名前のルートドメインのみを使用している場合、これは動作しないので、結果としてサポートされていません。 詳細については、[このサポート技術情報の記事に](https://support.microsoft.com/kb/300684/en-us)記載されています。
  
Skype for Business Server 2015 では、ドメイン名の変更もサポートされていません。 実際にこれを行う必要がある場合は、Skype for Business Server 2015 をアンインストールし、ドメイン名を変更した後、Skype for Business Server 2015 を再インストールする必要があります。
  
最後に、ロックダウンされた AD DS 環境があるドメインを処理することになります。 詳細については、「展開」ドキュメントの「Skype for Business Server 2015 をそのような環境に展開する」を参照してください。
  
### <a name="ad-topologies"></a>AD トポロジ

Skype for Business Server 2015 のサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用した Skype for Business リソースフォレストトポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソースフォレストトポロジの複数フォレスト
    
ここでは、環境内にあるトポロジを判断するのに役立つ図と説明、または Skype for Business Server 2015 をインストールする前にセットアップする必要があるものについて説明します。 簡単にするために、キーも含めています。
  
![は、Skype for Business トポロジの図で使用されるアイコンの鍵となります。](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![単一のドメインを含む Active Directory 単一フォレストの図](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これよりも簡単ではありませんが、単一のドメインフォレストで、これは一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、および複数ドメインの図](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は1つのフォレストを示していますが、1つ以上の子ドメインも持っています (この例では3つあります)。 そのため、ユーザーが作成されるドメインは、Skype for Business Server 2015 が展開されているドメインとは異なる場合があります。 このことを気にするのはなぜですか。 Skype for Business Server のフロントエンドプールを展開するときは、そのプール内のすべてのサーバーが単一のドメイン内に存在する必要があることを覚えておくことが重要です。 Skype for Business Server での Windows ユニバーサル管理者グループのサポートにより、クロスドメイン管理を行うことができます。
  
上記の図に戻ると、あるドメインのユーザーが、同じドメインまたは別のドメインから、それらのユーザーが子ドメインにある場合でも、Skype for Business Server プールにアクセスできることがわかります。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一フォレスト、複数ツリー、および不整合の名前空間の図](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図のようなトポロジを使用していて、フォレストが1つあり、そのフォレスト内に異なる AD 名前空間を持つ複数のドメインがある場合があります。 その場合は、この図のように、Skype for Business Server 2015 にアクセスする3つの異なるドメインにユーザーがいるので、この図を使用することをお勧めします。 実線は、自分のドメインにある Skype for Business Server プールにアクセスしていることを示します。点線は、異なるツリーでプールに送られることを示しています。
  
ご覧のとおり、同じドメイン、同じツリー、または別のツリー内のユーザーは、プールに正常にアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレストトポロジ図の複数のフォレスト](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 は、中央フォレストトポロジで構成された複数のフォレストをサポートします。 この点について理解していない場合は、トポロジ内の中央フォレストは、他のフォレスト内のユーザーを表すために it 内のオブジェクトを使用し、フォレスト内のユーザーのユーザーアカウントをホストします。
  
これはどのように動作しますか? また、ディレクトリ同期製品 (Forefront Identity Manager、FIM など) は、組織のユーザーアカウントをその存在を通して管理します。 フォレストからアカウントを作成または削除すると、その変更は中央フォレスト内の対応する連絡先に同期されます。
  
お客様の AD インフラストラクチャがこのトポロジに移行するのが簡単ではないかもしれませんが、既にある場合、またはフォレストインフラストラクチャを計画している場合は、この方法が適しています。 Skype for Business Server 2015 の展開を単一のフォレスト内で集中管理することができますが、ユーザーは任意のフォレスト内の他のユーザーの検索、通信、およびプレゼンスの表示ができます。 すべてのユーザー連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソースフォレストトポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソースフォレストのトポロジ図における複数のフォレスト](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソースフォレストトポロジもサポートされています。ここで、フォレストは、Microsoft Exchange Server および Skype for Business Server 2015 などのサーバーアプリケーションを実行するための専用になっています。 このリソースフォレストは、アクティブなユーザーオブジェクトの同期表現もホストしますが、ログオンが有効なユーザーアカウントはホストしません。 そのため、リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境であり、リソースフォレストとのフォレストレベルの信頼関係があります。
  
Exchange Server は、Skype for Business Server と同じリソースフォレストまたは別のフォレストに展開できます。
  
この種類のトポロジで Skype for Business Server 2015 を展開するには、ユーザーフォレスト内の各ユーザーアカウントに対してリソースフォレストに1つの無効なユーザーオブジェクトを作成します (Microsoft Exchange Server が既に環境内にある場合は、このような操作が行われます)。 その後、ユーザーアカウントをライフサイクルを通じて管理するディレクトリ同期ツール (Forefront Identity Manager、FIM など) が必要になります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用した Skype for Business リソースフォレストトポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは、「 [Skype For business リソースフォレストトポロジの複数フォレスト](environmental-requirements.md#BKMK_multipleforestopology)」で説明されているトポロジに似ています。
  
このトポロジでは、1つ以上のユーザーフォレストがあり、Skype for Business Server は専用のリソースフォレストに展開されています。 Exchange Server は、社内の同じリソースフォレストまたは異なるフォレストに展開でき、Exchange Online とのハイブリッド用に構成されている場合や、電子メールサービスがオンプレミスのアカウントに対して Exchange Online で排他的に提供される場合があります。 このトポロジで使用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソースフォレストトポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2つの AD フォレスト、1つのユーザーフォレスト、1つのリソースフォレストを示します。 2つのフォレストには、信頼関係があります。 Azure AD Connect を使用して、Microsoft 365 または Office 365 と同期されます。 すべてのユーザーは、Microsoft 365 または Office 365 経由で Skype for Business に対して有効になっています。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、社内に複数のフォレストがあり、リソースフォレストトポロジがあります。 Active Directory フォレスト間に完全な信頼関係があります。 Azure Active Directory Connect ツールは、オンプレミスのユーザーフォレストと Microsoft 365 または Office 365 間でアカウントを同期するために使用されます。
  
 また、組織には Microsoft 365 または Office 365 があり、 [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836)を使用してオンプレミスアカウントを microsoft 365 または office 365 と同期させます。 Skype for business が有効になっているユーザーは、Microsoft 365 または Office 365 と Skype for Business Online を介して有効になります。 Skype for Business Server がオンプレミスで展開されていません。
  
シングルサインオン認証は、ユーザーフォレストにある Active Directory フェデレーションサービスファームによって提供されます。
  
このシナリオでは、exchange on-premises、Exchange Online、ハイブリッド Exchange ソリューションを展開するか、または Exchange をまったく展開しないようにすることがサポートされています。 (図は Exchange オンプレミスのみを示していますが、他の Exchange ソリューションも完全にサポートされています。)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソースフォレストトポロジ内の複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1つまたは複数のオンプレミスのユーザーフォレストが存在し、Skype for Business が専用のリソースフォレストに展開され、Skype for business Online とのハイブリッドモード用に構成されています。 Exchange Server は、オンプレミスのと同じリソースフォレストまたは異なるフォレストに展開できます。また、Exchange Online とのハイブリッド用に構成されている場合もあります。 または、社内アカウントの Exchange Online のみが電子メールサービスを提供することがあります。
  
詳細については、「[ハイブリッド Skype For business の複数フォレスト環境の構成](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)」を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

次の理由で、Skype for Business Server 2015 には DNS が必要です。
  
- DNS を使用すると、Skype for Business Server 2015 は内部サーバーまたはプールを検出できるようになり、サーバー間の通信が可能になります。
    
- DNS により、クライアントコンピューターは SIP トランザクションに使用されているフロントエンドプールまたは Standard Edition サーバーを検出できるようになります。
    
- 会議の単純な Url を、それらの会議をホストしているサーバーに関連付けます。
    
- DNS を使用すると、外部ユーザーとクライアントコンピューターは、インスタントメッセージング (IM) または会議用のエッジサーバーまたは HTTP リバースプロキシに接続できます。
    
- ログインしていない統合コミュニケーション (UC) デバイスでは、デバイス更新 web サービスを実行しているフロントエンドプールまたは Standard Edition サーバーで、更新プログラムを取得してログを送信することができます。
    
- DNS を使用すると、モバイルクライアントは、ユーザーが自分のデバイス設定で Url を手動で入力する必要がなく、web サービスリソースを自動的に検出できます。
    
- DNS 負荷分散で使用されます。
    
Skype for Business Server 2015 は、国際化ドメイン名 (Idn) をサポートしていないことに注意することが重要です。
  
また、DNS では、Skype for Business Server 2015 で使用されているサーバーに構成されているコンピューター名と同じ名前にする必要があります。 具体的には、環境内に短縮名を含めることはできません。また、トポロジビルダーの Fqdn を指定する必要があります。
  
これは、既にドメインに参加しているコンピューターでは論理のように見えますが、エッジサーバーがドメインに参加していない場合は、ドメインサフィックスを持たない短い名前の既定値を持つことができます。 そのような場合は、DNS またはエッジサーバー、あるいはその他の Skype for Business Server 2015 サーバーまたはプールのいずれかに該当しないことを確認してください。
  
そして、必ずしも Unicode 文字またはアンダースコアは使用しないでください。 標準文字 (A ~ Z、a ~ z、0-9、ハイフン) は、外部 DNS および公共の証明機関によってサポートされる予定です (証明書の SN に Fqdn を割り当てる必要があります)。このため、このことを念頭に置いて、grief の多くのことができます。
  
ネットワークの DNS 要件の詳細については、「計画」のドキュメントの「[ネットワーク](../../plan-your-deployment/network-requirements/network-requirements.md)」セクションを参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

を展開する前に実行できる最も重要なことの1つは、証明書が順番になっていることを確認することです。 Skype for Business Server 2015 は、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) を必要とします。 基本的には、標準化された方法で安全に通信するために、Skype for Business Server は、証明機関 (CAs) によって発行された証明書を使用します。
  
以下に、Skype for Business Server 2015 が証明書を使用する場合のいくつかの点を示します。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出のフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザーアクセス
    
- Web アプリケーションと Outlook Web Access (OWA) との会話
    
そのためには、証明書の計画が必要です。 次に、証明書を要求するときに考慮する必要があるいくつかの項目の一覧を見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書は、オペレーティングシステムでサポートされている署名アルゴリズムを使用して署名する必要があります。 Skype for Business Server 2015 は、ダイジェストサイズ (224、256、384、および512ビット) の SHA-1 および SHA-1 スイートをサポートしており、オペレーティングシステムの要件を満たしているか、それを超えています。
    
- Skype for Business Server 2015 を実行している内部サーバーでは、自動登録がサポートされています。
    
- Skype for Business Server 2015 エッジサーバーでは、自動登録がサポートされていません。
    
- Windows Server 2003 の CA に対して Web ベースの証明書要求を送信する場合は、Windows Server 2003 (SP2 適用済み) または Windows XP を実行しているコンピューターから送信する必要があります。
    
> [!NOTE]
> KB922706 は、Windows Server 2003 証明書サービス web 登録に対して web 証明書を登録する際の問題を解決することをサポートしていますが、windows server 2008、Windows Vista、または Windows 7 を使用して Windows Server 2003 CA から証明書を要求することはできません。 
  
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムを使用することはサポートされていません。その他の問題の中では、ログイン時にエラーが発生し、転送の問題が発生する可能性があります。 

> [!NOTE]
> Skype for Business Server 2015 は、CNG 証明書をサポートしていません。
  
- 1024、2048、4096の暗号化キーの長さがサポートされています。 2048以上のキーの長さは推奨されています。
    
- 既定のダイジェスト、つまりハッシュ署名は RSA です。 ECDH_P256、ECDH_P384、および ECDH_P521 の各アルゴリズムもサポートされています。
    
そのため、多くの場合、CA からの証明書を要求することで、さまざまなレベルの安心感があります。 可能な限り簡単に計画を立てるために、次に示す追加のガイダンスが提供されます。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバーの証明書

ほとんどの内部サーバーに対して証明書が必要になります。多くの場合、内部 CA (ドメインにあるもの) から証明書を取得します。 必要な場合は、外部 CA (インターネット上にある CA) からこれらの証明書を要求できます。 アクセス先のパブリック CA がわからない場合は、[統合コミュニケーション証明書パートナー](/SkypeForBusiness/certification/services-ssl)の一覧を確認できます。
  
また、Skype for Business Server 2015 が、Microsoft Exchange Server などの他のアプリケーションやサーバーと通信するときにも証明書が必要になります。 これは明らかに、他のアプリやサーバーがサポートされている方法で使用できる証明書である必要があります。 Skype for Business Server 2015 およびその他の Microsoft 製品は、サーバー間の認証と承認のために Open Authorization (OAuth) プロトコルをサポートしています。 これに関心がある場合は、OAuth および Skype for business Server 2015 に関する追加の計画に関する記事があります。
  
また、Skype for Business Server 2015 には、SHA-256 暗号化ハッシュ関数を使用して署名された証明書を (必要とせずに) サポートしています。 256を使用して外部アクセスをサポートするには、外部証明書を、SHA-1-256 を使用してパブリック CA から発行する必要があります。
  
わかりやすくするために、次の表に、Standard Edition サーバー、フロントエンドプール、およびその他の役割に関する証明書の要件を、例として架空の contoso.com を使用して示します (環境によっては他のものを使用している可能性があります)。 これらはすべて標準の web サーバー証明書で、エクスポートできない秘密キーが含まれています。 その他の注意事項:
  
- サーバー拡張キー使用法 (EKU) は、証明書ウィザードを使用して証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューターストア内で一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成した場合は、証明書のサブジェクトの別名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN = se01。SAN = se01  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |Standard edition サーバー Standard Edition サーバーでは、サーバーの FQDN はプールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証に使用することもできます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = se01。SAN = se01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = se01。SAN = se01。SAN = \* . contoso.com  <br/> |トポロジビルダーで内部 web FQDN を上書きすることはできません。  <br/> 複数の会議の簡易 Url がある場合は、それらすべてを San として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> •ダイヤルインの簡易 URL  <br/> • SIP ドメインごとに単純な Url を満たす  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = se01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01。SAN = webcon01。SAN = \* . contoso.com  <br/> |複数の会議の簡易 Url がある場合は、それらすべてをサブジェクトの別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンドプール内のフロントエンドサーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効にされている場合は、証明書ウィザードで、サポートされている各 SIP ドメイン FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要となる場合は、sip.sipdomain のエントリ (存在するそれぞれの SIP 用) も必要となります。  <br/> |SN = eepool。SAN = eepool、SAN = ee01  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクト名の別名に自動的に追加されます。  <br/> この証明書は、サーバー間認証に使用することもできます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じではない)  <br/> •サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = ee01。SAN = ee01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01。SAN = ee01。SAN = \* . contoso.com  <br/> |複数の会議の簡易 Url がある場合は、それらすべてをサブジェクトの別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = ee01。SAN = webcon01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01。SAN = webcon01。SAN = \* . contoso.com  <br/> |複数の会議の簡易 Url がある場合は、それらすべてをサブジェクトの別名として含める必要があります。  <br/> 簡易 URL エントリにはワイルドカード エントリがサポートされます。  <br/> |
   
ディレクターの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |ディレクター プール  <br/> |ディレクターの FQDN、ディレクタープールの FQDN。  <br/> このプールがクライアントの自動ログオンサーバーであり、グループポリシーで厳密な DNS マッチングが必要な場合は、microsoft.rtc.management.xds.sipdomain のエントリも必要です (SIP ドメインごとに)。  <br/> |pool.contoso.com;SAN = dir01  <br/> このディレクター プールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要となる場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要となります。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> •サーバーの FQDN  <br/> • Skype for Business プールの FQDN  <br/> AND  <br/> •簡単な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> •管理者の簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |SN = dir01。SAN = dir01。SAN = contoso .com。SAN = fabrikam .comSAN = ダイヤルイン。SAN = 管理  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01。SAN = dir01 SAN = \* . contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> AND  <br/> • SIP ドメインごとに単純な Url を満たす  <br/> •ダイヤルインの簡易 URL  <br/> または  <br/> •簡易 Url のワイルドカードエントリ  <br/> |ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーとは別のものにする必要があります。  <br/> SN = dir01。SAN = directorwebcon01、SAN = 「contoso .com」SAN = fabrikam .comSAN = ダイヤルイン .com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01。SAN = directorwebcon01 SAN = \* . contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プールメンバーサーバーの FQDN  <br/> |SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01  <br/> |
   
存続可能ブランチアプライアンスの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクト名の別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定値  <br/> |アプライアンスの FQDN  <br/> |SIP。 \<microsoft.rtc.management.xds.sipdomain \> (SIP ドメインごとに1つのエントリのみが必要)  <br/> |SN = sba01;SAN = sip。SAN: fabrikam. .com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>常設チャットサーバーの証明書

常設チャットサーバーをインストールする場合、Skype for Business Server 2015 内部サーバーが使用する証明書と同じ CA が発行する証明書が必要になります。 これは、ファイルのアップロード/ダウンロード用の常設チャット Web サービスを実行している各サーバーに対して実行する必要があります。 常設チャットインストールを開始する前に、必要な証明書を取得することを強くお勧めします。また、CA が外部にある場合は (これらのことは、発行に少し時間がかかる可能性があります)。
  
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザーアクセスの証明書 (エッジ)

Skype for Business Server 2015 では、アクセスおよび web 会議エッジの外部インターフェイスに対する**単一のパブリック証明書**の使用と、エッジサーバー経由で提供される音声ビデオ認証サービスをサポートしています。 通常、エッジ内部インターフェイスは内部 CA から発行されたプライベート証明書を使用しますが、必要に応じて、信頼された CA からのパブリック証明書も使用できます。
  
リバースプロキシ (RP) は、パブリック証明書を使用することもできます。また、RP からクライアントへの通信を暗号化し、HTTP (より正確に HTTP 経由の TLS) を使用して、RP を内部サーバーに送信します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

Mobility を展開していて、モバイルクライアントの自動検出をサポートしている場合は、モバイルクライアントからのセキュリティで保護された接続をサポートするために、証明書に追加のサブジェクト代替名エントリを含める必要があります。
  
どの証明書ですか? ここでは、証明書を自動検出するために SAN 名が必要になります。
  
- ディレクター プール
    
- フロント エンド プール
    
- リバース プロキシ
    
以下の各表で、詳細を示します。
  
ここでは、計画が少し前になっていますが、モビリティを展開しないで Skype for Business Server 2015 を展開した場合は、既に環境に証明書を持っている場合は、次の行が表示されることがあります。 通常、内部 CA を経由してそれらを再発行するのは非常に簡単ですが、パブリック CA からのパブリック証明書を使用すると、もう少し上がることができます。
  
これが表示されている場合に、多数の SIP ドメインがある場合 (SAN をより高価に追加することになります)、HTTPS (既定の構成) ではなく、初期自動検出サービス要求に HTTP を使用するようにリバースプロキシを構成できます。 この詳細については、「Mobility for Mobility」のトピックを参照してください。
  
ディレクタープールおよびフロントエンドプールの証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN = lyncdiscoverinternal。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
また、SAN = を使用することもでき \* ます。 \<microsoft.rtc.management.xds.sipdomain\>
  
リバースプロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。 \<microsoft.rtc.management.xds.sipdomain\>  <br/> |
   
この SAN は、リバースプロキシ上の SSL リスナーに割り当てられている証明書に割り当てる必要があります。
  
> [!NOTE]
> リバースプロキシリスナーは、外部 Web サービスの URL に San を使用します。 たとえば、ディレクターが展開されている場合は、SAN = skypewebextpool01 および dirwebexternal.contoso.com があります (オプション)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2015 は、すべてのファイルストレージに対して同じファイル共有を使用できます。 次の点に注意する必要があります。
  
- ファイル共有は直接接続ストレージ (DAS) または記憶域エリアネットワーク (SAN) のどちらかに配置する必要があります。これには、分散ファイルシステム (DFS) と、ファイルストア用の独立したディスク (RAID) の冗長配列が含まれています。 Windows Server 2012 の DFS の詳細については、[この dfs ページ](https://technet.microsoft.com/library/jj127250.aspx)を参照してください。
    
- 共有クラスターには、ファイル共有を使用することをお勧めします。 いずれかを使用している場合は、Windows Server 2012 または Windows Server 2012 R2 をクラスター化する必要があります。 Windows Server 2008 R2 も受け入れられます。 最新の Windows の利点 以前のバージョンには、すべての機能を有効にするための適切な権限がない場合があります。 クラスターアドミニストレーターを使用してファイル共有を作成することができます。このため、このような詳細情報については、「[クラスターでファイル共有を作成する方法](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster)」を参照してください。
    
> [!CAUTION] 
> ネットワーク接続ストレージ (NAS) をファイル共有として使用することはサポートされていないため、上記のオプションのいずれかを使用してください。 
  
