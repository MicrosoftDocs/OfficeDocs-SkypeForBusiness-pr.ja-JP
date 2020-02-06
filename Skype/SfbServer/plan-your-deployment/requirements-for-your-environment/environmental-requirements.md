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
description: '概要: Skype for Business Server 2015 のサーバー以外の要件を構成します。 これらに該当するのは、Active Directory、DNS、証明書、ファイル共有など、展開を実行する前に構成しようとするさまざまな事項です。'
ms.openlocfilehash: 7af4587dfef237a6449dbfa9a271910398ec8a41
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801907"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>Environmental requirements for Skype for Business Server 2015
 
**概要:** Skype for Business Server 2015 のサーバー以外の要件を構成します。 これらに該当するのは、Active Directory、DNS、証明書、ファイル共有など、展開を実行する前に構成しようとするさまざまな事項です。
  
Skype for Business Server 2015 の環境要件を教えてください。 ここでは、直接サーバーに関連していないすべての項目について説明しています。そのため、クリックする必要はありません。 サーバーの前提条件をお探しの場合は、「 [Skype For Business server 2015 ドキュメントのサーバー要件](server-requirements.md)」を参照してください。[ネットワーキングの計画](../../plan-your-deployment/network-requirements/network-requirements.md)についても別々に説明します。 それ以外の場合は、この記事で説明していることになります。
  
- [Active Directory](environmental-requirements.md#AD)
  
- [ドメイン ネーム システム (DNS)](environmental-requirements.md#DNS)
  
- [証明書](environmental-requirements.md#Certs)
  
- [ファイル共有](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

サーバーおよびサービスの構成データの多くは、Skype for Business Server 2015 の中央管理ストアに保存されていますが、まだ Active Directory に保存されているものもあります。
  
|**Active Directory オブジェクト**|**オブジェクトの種類**|
|:-----|:-----|
|スキーマ拡張  <br/> |ユーザー オブジェクトの拡張  <br/> |
||以前サポートされているバージョンとの下位互換性を維持するための、Lync Server 2013 および Lync Server 2010 用の拡張機能。  <br/> |
|データ  <br/> |ユーザーの SIP URI と他のユーザー設定  <br/> |
||アプリケーションの連絡先オブジェクト (返信グループアプリケーション、会議アテンダントアプリケーションなど)  <br/> |
||下位互換性について公開されたデータ。  <br/> |
||中央管理ストアのサービス制御ポイント (SCP)。  <br/> |
||Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)。  <br/> |
   
### <a name="os-for-domain-controllers"></a>ドメイン コントローラー用の OS

どのドメイン コントローラー用 OS を使用できるかについては、以下の一覧を参照してください。

- Windows Server 2019 (Skype for Business Server 2015 累積更新プログラム5以降が必要です)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
ここで、Skype for Business Server 2015 に展開するドメインのドメイン機能レベルと、Skype for Business Server 2015 を展開したすべてのフォレストの機能レベルは、次のいずれかにする必要があります。

- Windows Server 2019 (Skype for Business Server 2015 累積更新プログラム5以降が必要です)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
これらの環境には読み取り専用ドメインコントローラーがありますか? また、書き込み可能なドメインコントローラーも使用できる限り、ご確認ください。
  
Skype for Business Server 2015 では、単一のラベルが付いたドメインをサポートしていないことを知っておくことが重要です。 単一ラベルのドメインがどのようなものかを把握しておいてください。 Contoso. .local というラベルの付いたルートドメインを持っている場合、これは問題ありません。 ローカルという名前のルートドメインがあり、それが機能していない場合、結果としてサポートされません。 詳細については、[このサポート技術情報の記事で](https://support.microsoft.com/kb/300684/en-us)記載されています。
  
Skype for Business Server 2015 では、ドメイン名の変更もサポートされていません。 実際にこの操作を行うには、Skype for Business Server 2015 をアンインストールし、ドメイン名の変更を行ってから、Skype for Business Server 2015 を再インストールする必要があります。
  
最後に、ロックダウンされた AD DS 環境でドメインを処理している可能性があります。これがすべて適切です。 Skype for Business Server 2015 を展開ドキュメントのそのような環境に展開する方法については、こちらを参照してください。
  
### <a name="ad-topologies"></a>Active Directory トポロジ

Skype for Business Server 2015 のサポートされているトポロジは次のとおりです。
  
- 単一のドメインを含む単一のフォレスト
    
- 単一のツリーと複数のドメインを含む単一のフォレスト
    
- 複数のツリーと不整合の名前空間を含む単一のフォレスト
    
- 中央フォレスト トポロジの複数のフォレスト
    
- リソース フォレスト トポロジの複数のフォレスト
    
- Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
    
- Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
    
使用している環境にどのようなトポロジがあるかを判断するのに役立つ図と説明、および Skype for Business Server 2015 をインストールする前にセットアップする必要があることについて説明します。 シンプルな状態を維持するために、キーも含めています。
  
![Skype for Business トポロジ図に使用される主なアイコン](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>単一のドメインを含む単一のフォレスト

![ドメインが 1 つである Active Directory の単一フォレストの図](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
これまで以上に簡単にはなりません。1つのドメインフォレストであり、これは一般的なトポロジです。
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>単一のツリーと複数のドメインを含む単一のフォレスト

![単一のフォレスト、単一のツリー、複数のドメインがある図](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
この図は、1つのフォレストを示していますが、1つ以上の子ドメインも含まれています (この例では3つあります)。 そのため、ユーザーが作成されるドメインは、Skype for Business Server 2015 の展開先のドメインとは異なる場合があります。 どうしたらよいのでしょうか。 Skype for Business Server フロントエンドプールを展開するときに、そのプール内のすべてのサーバーが単一のドメインに存在している必要があることに注意してください。 Skype for Business Server での Windows ユニバーサル管理者グループのサポートにより、ドメイン間管理を行うことができます。
  
上の図に戻ると、あるドメインのユーザーが、同じドメインまたは別のドメインから Skype for Business Server プールにアクセスできることを確認できます。それらのユーザーが子ドメインにいる場合でも同じです。
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>複数のツリーと不整合の名前空間を含む単一のフォレスト

![単一のフォレスト、複数のツリー、不整合の名前空間がある図](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
この図と同じように、フォレストが1つあり、そのフォレスト内に複数のドメインがあり、別々の AD 名前空間を持つトポロジがある場合があります。 このような場合、3つの異なるドメインのユーザーが Skype for Business Server 2015 にアクセスしているので、この図をお勧めします。 実線は、自分のドメインで Skype for Business サーバープールにアクセスしていることを示しますが、破線は、異なるツリーでプールに移動していることを示します。
  
図のように、同一のドメイン、同一のツリーだけでなく、異なるツリーのユーザーも正常にプールにアクセスできます。
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>中央フォレスト トポロジの複数のフォレスト

![中央フォレスト トポロジの複数のフォレストの図](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2015 は、中央フォレストトポロジで構成されている複数のフォレストをサポートしています。 自分が持っていることがわからない場合、トポロジの中央のフォレストでは、他のフォレストのユーザーを表すためのオブジェクトを使用し、フォレスト内のユーザーのユーザーアカウントをホストします。
  
動作のしくみ また、ディレクトリ同期製品 (Forefront Identity Manager、FIM など) では、組織のユーザーアカウントがその存在を通じて管理されます。 フォレストからアカウントが作成または削除されると、その変更はセントラルフォレスト内の対応する連絡先に同期されます。
  
お客様の広告インフラストラクチャが、このトポロジへのインプレース移動は簡単ではない場合もありますが、既に存在している場合、またはフォレストインフラストラクチャを計画している場合は、この方法が適しています。 Skype for Business Server 2015 の展開を1つのフォレストにまとめることができます。ユーザーは、任意のフォレストの他のユーザーの検索、通信、表示を行うことができます。 すべてのユーザーの連絡先の更新は、同期ソフトウェアで自動的に処理されます。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Skype for Business リソース フォレスト トポロジの複数のフォレスト
<a name="BKMK_multipleforestopology"> </a>

![リソース フォレスト トポロジ内に複数のフォレストがある図](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
リソースフォレストのトポロジもサポートされています。ここでは、Microsoft Exchange Server や Skype for Business Server 2015 など、サーバーアプリケーションの実行専用のフォレストがあります。 このリソースフォレストは、アクティブなユーザーオブジェクトの同期表現もホストしますが、ログオン可能なユーザーアカウントはホストしません。 そのため、リソースフォレストは、ユーザーオブジェクトが存在する他のフォレストの共有サービス環境であり、リソースフォレストとのフォレストレベルの信頼関係があります。
  
Exchange Server は、Skype for Business Server と同じリソースフォレスト、または別のフォレストに展開できることに注意してください。
  
この種類のトポロジで Skype for Business Server 2015 を展開するには、ユーザーフォレスト内の各ユーザーアカウントのリソースフォレストに無効なユーザーオブジェクトを1つ作成します (Microsoft Exchange Server が既に環境にある場合は、これが自動的に実行されることがあります)。 その後、ユーザーアカウントをライフサイクルを通じて管理するディレクトリ同期ツール (Forefront Identity Manager、FIM など) が必要になります。
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online を使用する Skype for Business リソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このトポロジは「[Skype for Business リソース フォレスト トポロジの複数フォレスト](environmental-requirements.md#BKMK_multipleforestopology)」で説明されるトポロジと同様のものです。
  
このトポロジには、1つ以上のユーザーフォレストがあり、Skype for Business Server は専用リソースフォレストに展開されます。 Exchange Server は、同じリソースフォレストまたは別のフォレストに展開して、Exchange Online とのハイブリッド用に構成することができます。また、メールサービスは、オンプレミスアカウントの Exchange Online でのみ提供されます。 このトポロジで利用できる図はありません。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Skype for Business Online および Azure Active Directory Connect を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

![2 つの AD フォレスト (ユーザー フォレストとリソース フォレスト) があります。これらの 2 つのフォレストの間には、信頼関係が確立されています。これらの 2 つのフォレストは、Azure AD Connect を使用して Office 365 と同期されます。すべてのユーザーは、Office 365 経由で Skype for Business を利用できます。](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
このシナリオでは、リソース フォレスト トポロジを使用するオンプレミスの複数のフォレストが存在し、Active Directory フォレスト間には完全な信頼関係がある場合を考えます。オンプレミス ユーザー フォレストと Office 365 との間のアカウントを同期するために、Azure Active Directory Connect ツールが使用されます。
  
 組織にも Office 365 があり、 [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836)を使用して、オンプレミスアカウントを office 365 と同期します。 Skype for Business が有効になっているユーザーは、Office 365 および Skype for Business Online によって有効にされています。 Skype for Business Server はオンプレミスでは展開されません。
  
シングルサインオン認証は、ユーザーフォレストにある Active Directory フェデレーションサービスファームによって提供されます。
  
このシナリオでは、exchange をオンプレミス、Exchange Online、ハイブリッド Exchange ソリューション、または Exchange が展開されていない状態で展開することがサポートされています。 (図面には Exchange のオンプレミスのみが表示されますが、その他の Exchange ソリューションも完全にサポートされています)。
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>ハイブリッド Skype for Business を使用するリソース フォレスト トポロジの複数フォレスト
<a name="BKMK_multipleforestopology"> </a>

このシナリオでは、1つ以上のオンプレミスのユーザーフォレストがあり、Skype for Business は専用のリソースフォレストに展開され、skype for business Online とのハイブリッドモード用に構成されています。 Exchange Server は、同じリソースフォレストまたは別のフォレストに展開することができます。また、exchange Online とのハイブリッド用に構成することもできます。 または、社内アカウントの Exchange Online によってのみ、メールサービスが提供されることがあります。
  
詳細については、「[ハイブリッド Skype For business 用にマルチフォレスト環境を構成](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)する」を参照してください。
  
## <a name="domain-name-system-dns"></a>ドメイン ネーム システム (DNS)
<a name="DNS"> </a>

Skype for Business Server 2015 には DNS が必要です。次の理由が考えられます。
  
- DNS によって、Skype for Business Server 2015 は内部サーバーまたはプールを検出できるため、サーバー間の通信が可能になります。
    
- DNS により、クライアントコンピューターは SIP トランザクションに使用されているフロントエンドプールまたは Standard Edition サーバーを検出できます。
    
- 会議用の簡易 URL と、これらの会議をホストするサーバーが関連付けられます。
    
- DNS を使うと、外部ユーザーとクライアントコンピューターが、インスタントメッセージング (IM) または会議のために、エッジサーバーまたは HTTP リバースプロキシに接続できます。
    
- ログインしていないユニファイドコミュニケーション (UC) デバイスでは、デバイス更新 web サービスが実行されているフロントエンドプールまたは Standard Edition サーバーで、更新プログラムを取得してログを送信できます。
    
- DNS を使用すると、モバイル クライアントでは、デバイス設定で URL を手動入力しなくても Web サービス リソースを自動的に検出できます。
    
- また、DNS は DNS ロード バランシングで使用されます。
    
Skype for Business Server 2015 は、国際化ドメイン名 (Idn) をサポートしていないことに注意してください。
  
また、DNS の名前は、Skype for Business Server 2015 で使用されているサーバー上で構成されているコンピューター名と同じであることを覚えておくことが非常に重要です。 具体的には、環境内に短い名前を設定することはできません。また、トポロジビルダーの Fqdn が必要です。
  
これは、既にドメインに参加しているコンピューターには関係ありませんが、ドメインに参加していないエッジサーバーがある場合は、既定値としてドメインサフィックスが含まれていない可能性があります。 この問題について、DNS、またはエッジサーバー、または Skype for Business Server 2015 サーバーまたはプールのどちらでも、そうしないようにしてください。
  
また、必ずしも Unicode 文字またはアンダースコアは使用しないでください。 標準文字 (A-z、a-z、0-9、ハイフン) は、外部 DNS と公共の証明機関によってサポートされているものです (証明書の SN に Fqdn を割り当てる必要があります)。そのため、お客さんが grief をお使いになる場合は、これを念頭に置いて名前を付けます。
  
ネットワークの DNS 要件に関するその他の情報については、「計画」ドキュメントの「[Networking](../../plan-your-deployment/network-requirements/network-requirements.md)」を参照してください。
  
## <a name="certificates"></a>証明書
<a name="Certs"> </a>

展開の前の最も重要な作業の 1 つは、証明書を用意することです。 Skype for Business Server 2015 には、トランスポート層セキュリティ (TLS) および相互トランスポート層セキュリティ (MTLS) 接続用の公開キー基盤 (PKI) が必要です。 基本的に、標準化された方法で安全に通信するために、Skype for Business Server は証明機関 (Ca) によって発行された証明書を使用します。
  
Skype for Business Server 2015 では、次のような用途で証明書が使用されます。
  
- クライアントとサーバー間の TLS 接続
    
- サーバー間の MTLS 接続
    
- パートナーの自動 DNS 検出を使用するフェデレーション
    
- インスタント メッセージング (IM) 用のリモート ユーザー アクセス
    
- 音声/ビデオ (AV) セッション、アプリケーション共有、および会議への外部ユーザー アクセス
    
- Web アプリケーションと Outlook Web Access (OWA) との会話
    
そのため、証明書の計画は必須です。 次に、証明書を要求するときに考慮しておく必要がある事項の一覧を見てみましょう。
  
- すべてのサーバー証明書がサーバーの承認 (サーバー EKU) をサポートしている必要がある。
    
- すべてのサーバー証明書に CRL 配布ポイント (CDP) を含める必要がある。
    
- すべての証明書が、オペレーティング システムでサポートされている署名アルゴリズムによって署名されている必要がある。 Skype for Business Server 2015 は、ダイジェストのサイズ (224、256、384、512ビット) の SHA-1 および SHA-1 スイートをサポートしており、オペレーティングシステムの要件を満たしているか、超えています。
    
- 自動登録は、Skype for Business Server 2015 を実行している内部サーバーでサポートされています。
    
- 自動登録は、Skype for Business Server 2015 Edge サーバーではサポートされていません。
    
- Web ベースの証明書要求を Windows Server 2003 CA に送信する場合は、Windows Server 2003 と SP2 または Windows XP を実行しているコンピューターから送信する必要があります。
    
> [!NOTE]
> KB922706 は、Windows Server 2003 証明書サービスの Web 登録について Web 証明書の登録に関わる問題解決をサポートしますが、Windows Server 2008、Windows Vista、または Windows 7 を使用して、Windows Server 2003 CA から証明書を要求できるようにはなりません。 
  
> [!NOTE]
> RSASSA-PSS 署名アルゴリズムの使用はサポートされておらず、数ある問題の中でも、ログイン時のエラーや着信転送時の問題につながる可能性があります。 

> [!NOTE]
> Skype for Business Server 2015 は CNG 証明書をサポートしていません。
  
- 暗証キーの長さとして 1024、2048、4096 がサポートされます。2048 以上のキーの長さはお勧めしません。
    
- 既定のダイジェストまたはハッシュ アルゴリズムは RSA です。ECDH_P256、ECDH_P384、ECDH_P521 のハッシュ アルゴリズムもサポートされます。
    
そのため、多くのことを考慮する必要があります。これは、CA から証明書を要求することによって、さまざまな方法でお使いいただけるということです。 お客様の計画をできるだけ簡単にするために、以下のガイダンスをさらに紹介します。
  
### <a name="certificates-for-your-internal-servers"></a>内部サーバー用の証明書

ほとんどの内部サーバーには証明書が必要ですが、ほとんどの場合、内部 CA (自分のドメインにあるもの) から証明書を取得します。 必要に応じて、外部の CA (インターネット上に存在する CA) から証明書を要求できます。 どのパブリック CA にアクセスすればよいか迷っている場合は、[ユニファイドコミュニケーション証明書パートナー](/SkypeForBusiness/certification/services-ssl)の一覧を確認できます。
  
また、Skype for Business Server 2015 が他のアプリケーションやサーバー (Microsoft Exchange Server など) と通信する場合は、証明書が必要になります。 この証明書は当然、サポートされている方法でこれらの他のアプリケーションやサーバーが使用できる証明書である必要があります。 Skype for Business Server 2015 およびその他の Microsoft 製品は、サーバー間の認証と承認のための Open Authorization (OAuth) プロトコルをサポートしています。 この項目に興味をお持ちの場合は、OAuth および Skype for Business Server 2015 のその他の計画記事をご覧ください。
  
Skype for Business Server 2015 には、(必要256とせずに) SHA-1 暗号化ハッシュ関数を使って署名された証明書のサポートも含まれています。 SHA-256 を使用する外部アクセスをサポートするには、SHA-256 を使用するパブリック CA が外部証明書を発行する必要があります。
  
簡単に行うことができるように、標準エディションサーバー、フロントエンドプール、その他の役割の証明書の要件は、例として使用されている架空の contoso.com を使って、次の表のようにします (おそらく使用していることに注意してください)。その他の環境の場合)。 これらはすべて、標準の web サーバー証明書であり、エクスポートできない秘密キーが含まれています。 その他の注意事項:
  
- サーバーの拡張キー使用法 (EKU) は、証明書ウィザードを使って証明書を要求するときに自動的に構成されます。
    
- 各証明書のフレンドリ名は、コンピューター ストアで一意である必要があります。
    
- 以下のサンプル名に従って、DNS で sipinternal.contoso.com または sipexternal.contoso.com を構成している場合は、証明書のサブジェクト代替名 (SAN) に追加する必要があります。
    
Standard Edition サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |Standard Edition servers Standard Edition server では、サーバーの FQDN はプールの FQDN と同じです。  <br/> このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01;SAN = se01;SAN =\*contoso.com  <br/> |トポロジビルダーでは、内部 web FQDN を上書きすることはできません。  <br/> 会議の簡易 URL が複数存在する場合、それらすべてを SAN として含める必要があります。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> •ダイヤルインの簡単な URL  <br/> • SIP ドメインあたりの単純な Url を満たす  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = se01;SAN = webcon01;SAN =\*contoso.com  <br/> |単純な Url を複数指定している場合は、そのすべてを件名の代替名として含めることができます。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
フロントエンドプールのフロントエンドサーバー用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|**コメント**|
|:-----|:-----|:-----|:-----|:-----|
|Default  <br/> |プールの FQDN  <br/> |プールの FQDN およびサーバーの FQDN  <br/> SIP ドメインが複数あり、自動クライアント構成が有効な場合は、証明書ウィザードによって、サポートされている各 SIP ドメインの FQDN が検出され、追加されます。  <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密なドメイン ネーム システム (DNS) マッチングが必要な場合は、sip.sipdomain のエントリ (所有する各 SIP ドメイン用) も必要となります。  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> このプールがクライアントの自動ログオン サーバーであり、グループ ポリシーで厳密な DNS マッチングが必要な場合は、SAN=sip.contoso.com、SAN=sip.fabrikam.com も必要です。  <br/> |このウィザードでは、セットアップ時に指定した SIP ドメインが検出され、サブジェクトの別名に自動的に追加されます。  <br/> また、この証明書はサーバー間認証でも使用できます。  <br/> |
|内部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN とは異なります)  <br/> •サーバー FQDN  <br/> • Skype for Business プールの FQDN  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01;SAN = ee01;SAN =\*contoso.com  <br/> |単純な Url を複数指定している場合は、そのすべてを件名の代替名として含めることができます。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
|外部 Web  <br/> |プールの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = ee01;SAN = webcon01;SAN =\*contoso.com  <br/> |単純な Url を複数指定している場合は、そのすべてを件名の代替名として含めることができます。  <br/> 簡易 URL エントリではワイルドカード エントリがサポートされます。  <br/> |
   
ディレクター用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |ディレクター プール  <br/> |ディレクタープールの FQDN の fqdn。  <br/> このプールがクライアント用の自動ログオンサーバーであり、グループポリシーでも DNS の厳密な一致が必要な場合は、sipdomain (SIP ドメインごとに) を入力する必要があります。  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> このディレクタープールがクライアント用の自動ログオンサーバーであり、かつ厳密な DNS 一致がグループポリシーで必要な場合は、SAN = sip-pstn を使用する必要もあります。サン = sip-pstn  <br/> |
|内部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •内部 web FQDN (サーバーの FQDN と同じ)  <br/> •サーバー FQDN  <br/> • Skype for Business プールの FQDN  <br/> および  <br/> •単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> •管理者 simple URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01;SAN = dir01 サン =\*. contoso.com  <br/> |
|外部 Web  <br/> |サーバーの FQDN  <br/> |次のうちのすべて:  <br/> •外部 web FQDN  <br/> および  <br/> • SIP ドメインあたりの単純な Url を満たす  <br/> •ダイヤルインの簡単な URL  <br/> または  <br/> •単純な Url のワイルドカードエントリ  <br/> |ディレクターの外部 web FQDN は、フロントエンドプールまたはフロントエンドサーバーと異なっている必要があります。  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> ワイルドカード証明書使用時:  <br/> SN = dir01;SAN = directorwebcon01 サン =\*. contoso.com  <br/> |
   
スタンドアロンの仲介サーバーの証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|既定  <br/> |プールの FQDN  <br/> |プールの FQDN  <br/> プール メンバー サーバーの FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance 用の証明書:
  
|**証明書**|**サブジェクト名/共通名**|**サブジェクトの別名**|**例**|
|:-----|:-----|:-----|:-----|
|Default  <br/> |アプライアンスの FQDN  <br/> |フェデレーション.\<SIPDOMAIN\> (SIP ドメインごとに1つのエントリしか必要ありません)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>常設チャット サーバー用の証明書

常設チャットサーバーをインストールする場合は、Skype for Business Server 2015 内部サーバーで使用されている CA と同じ CA によって発行された証明書が必要になります。 これは、ファイルアップロード/ダウンロード用の常設チャット Web サービスが実行されている各サーバーに対して実行する必要があります。 常設チャットのインストールを開始する前に、必要な証明書を持っていることを強くお勧めします。また、ご利用の CA が外部である場合は、こちらをご覧ください。
  
### <a name="certificates-for-external-user-access-edge"></a>外部ユーザー アクセス (エッジ) 用の証明書

Skype for Business Server 2015 では、access および web 会議エッジの外部インターフェイスに対する**1 つの公開証明書**と、エッジサーバー経由で提供される a/V 認証サービスをサポートしています。 通常、Edge 内部インターフェイスでは、内部 CA から発行されたプライベート証明書を使用しますが、必要に応じて、信頼できる CA から発行された公開証明書を使用することもできます。
  
またリバース プロキシ (RP) でも、パブリック証明書を使用して、RP からクライアントへの通信と RP から内部サーバーへの通信を、HTTP (厳密には TLS over HTTP) を使用して暗号化します。
  
### <a name="certificates-for-mobility"></a>モビリティ用の証明書

モバイルクライアントの自動検出をサポートしている場合、モバイルクライアントの自動検出をサポートするには、モバイルクライアントからのセキュリティで保護された接続をサポートするために、追加のサブジェクト代替名のエントリを追加する必要があります。
  
どの証明書ですか? 証明書を自動的に検出するには、次のような SAN 名が必要です。
  
- ディレクター プール
    
- フロントエンド プール
    
- リバース プロキシ
    
以下の各表で、仕様を示します。
  
ここでは、いくつかの事前計画を行うことができますが、モビリティを導入するのではなく、Skype for Business Server 2015 を展開したことがあります。これは、お使いの環境に既に証明書がある場合は、この行に表示されます。 通常、内部 CA を介した証明書の再発行は簡単ですが、パブリック CA のパブリック証明書を使用する場合は、多少コストが上がる可能性があります。
  
この情報が表示されていて、SIP ドメインが多数ある場合 (つまり、SAN をさらに追加するため)、HTTPS (既定値) ではなく、HTTP を使用するようにリバースプロキシを構成できます。構成)。 詳細については、「モビリティの計画」を参照してください。
  
ディレクタープールとフロントエンドプールの証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|内部自動検出サービス URL  <br/> |SAN = lyncdiscoverinternal。\<sipdomain\>  <br/> |
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
また、SAN =\*を使うこともできます。\<sipdomain\>
  
リバース プロキシ (パブリック CA) の証明書の要件:
  
|**説明**|**SAN エントリ**|
|:-----|:-----|
|外部自動検出サービス URL  <br/> |SAN = lyncdiscover。\<sipdomain\>  <br/> |
   
この SAN を、リバース プロキシ上の SSL リスナーに割り当てられる証明書に割り当てる必要があります。
  
> [!NOTE]
> リバースプロキシリスナーは、外部 Web サービスの URL に対して San を使用することになります。 ディレクターを展開した場合の例としては、「SAN = skypewebextpool01 and dirwebexternal.contoso.com」などがあります (これはオプションです)。 
  
## <a name="file-share"></a>ファイル共有
<a name="Fileshare"> </a>

Skype for Business Server 2015 は、すべてのファイルストレージに同じファイル共有を使用できます。 以下の点を考慮する必要があります。
  
- ファイル共有は、直接取り付け記憶域 (DAS) と記憶域ネットワーク (SAN) のいずれかに配置する必要があり、またファイル共有には、分散ファイル システム (DFS) だけでなくファイル ストア用の RAID (Redundant Array of Independent Disks) も含まれます。 Windows Server 2012 向け DFS について詳しくは、[この dfs のページ](https://technet.microsoft.com/library/jj127250.aspx)をご覧ください。
    
- ファイル共有の共有クラスターをお勧めします。 いずれかを使用している場合は、Windows Server 2012 または Windows Server 2012 R2 をクラスター化する必要があります。 Windows Server 2008 R2 も受け入れられます。 最新の Windows の理由 以前のバージョンには、すべての機能を有効にするための適切な権限がない場合があります。 クラスターアドミニストレーターを使ってファイル共有を作成することができます。この方法では、クラスターの記事[にファイル共有を作成する方法](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster)を説明します。
    
> [!CAUTION] 
> ファイル共有にネットワーク接続ストレージ (NAS) は使用できません。ファイル共有には、上記のいずれかの選択肢を利用してください。 
  

