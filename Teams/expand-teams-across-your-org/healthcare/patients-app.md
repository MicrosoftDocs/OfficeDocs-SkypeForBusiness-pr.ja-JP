---
title: 患者アプリケーションの概要
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: チーム患者の Microsoft アプリケーションの EHR の統合
ms.openlocfilehash: 25eb1b4ee09eec8395db2ac821d19624a508c937
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643124"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>マイクロソフトのチームに電子医療記録を統合します。

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

この資料は、一般的な医療情報の IT 開発者がマイクロソフトのチームに接続するための医療情報システムの上に FHIR Api を使用する必要です。 これは、結果、医療機関のニーズに合ったケア調整シナリオです。

この資料には、FHIR インタ フェースの仕様チーム患者の Microsoft アプリケーションと FHIR サーバーをセットアップして、開発の environment\tenant の患者のアプリケーションへの接続に必要な知識がドキュメント。 必要を理解するを選択したら、FHIR のサーバのマニュアル、サポートされているオプションのいずれかでなければなりません。
- を通じて自社の[CMI](https://datica.com/compliant-managed-integration/)製品) Datica
- 情報のクローバー型インターチェンジを[避けます FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox (を通じて、 [R ^ FHIR server](https://www.redoxengine.com/fhir/))
- ( [FHIR の Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)) から Dapasoft

> [!NOTE]
> このプロセスは、マイクロソフトのチーム管理センターまたは PowerShell コマンドレットを使用して、機能を有効にする手順を含んでいません。 構成は、サーバーまたはサービス側で FHIR と患者のアプリケーション クライアントでのみ行われます。

患者アプリケーションのアーキテクチャは、次に示します。

![患者のアプリケーション アーキテクチャ](../../media/patients-app-architecture.png)

次に、FHIR 専用データ アクセス層の患者のアプリケーションの要件について説明する FHIR サーバー (または、EHR は、FHIR Api を有効になって) 次を含む、患者のアプリケーションと統合するために満たす必要があります。

- ユーザー認証に関する要望
- 統合インターフェイスの機能および技術の要件
- パフォーマンスと信頼性に関する要望
- 患者のアプリケーションをサポートする FHIR リソースを期待
- プロセスを統合し、必要な活動モデル
- 自分自身と患者のアプリケーションのプライベートのプレビューで、顧客を登録する方法
- FHIR と患者のアプリケーションに直面したいくつかの一般的な課題を開始する方法
- 患者アプリケーションの次のイテレーションの将来的な要件

> [!NOTE]
> 次のセクションでは、単語「partner」または「相互運用パートナー」ために、サードパーティ製の FHIR を通じて患者アプリの EHR システムに統合し、一覧表示されている仕様と一致する FHIR サーバーの実装組織を参照していますください。

## <a name="functional-and-technical-requirements"></a>機能および技術要件  

### <a name="authentication"></a>認証  

アプリケーション レベルの認証*とユーザー レベルの認証はサポートされていません*より一般的にサポートされているデータの変換を実行し、FHIR を使用して EHR データへの接続を公開する方法も、EHR システムは、ユーザー レベルの認証を実装可能性があります。. 相互運用性サービス (パートナー) は、相互運用機能との統合 EHR データ、および相互運用機能サービスの利用者 (患者のアプリケーション) に渡される認証コンテキストがありません FHIR、適切なリソースと同じデータを公開するときに管理者特権へのアクセスを取得します。サービスまたはプラットフォームです。 患者のアプリケーションはユーザー レベルの認証を強制することはできませんが、患者のアプリケーションと相互運用機能のパートナーのサービスの間でのアプリケーションの認証をサポートしています。

アプリケーションの認証モデルは、以下に示します。

サービス サービスの認証を行うには、OAuth 2.0 の[クライアントの資格情報のフロー](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 パートナー サービスは、次を提供する必要があります。

1. パートナー サービスは、パートナー、患者、アプリケーションの生成を有効にして独自の client_id と client_secret、管理パートナーの認証サーバー上の認証登録ポータル経由でアカウントを作成するのには患者のアプリケーションを使用できます。
2. パートナー サービスを受け取り、検証、認証システムを所有している (認証) クライアントが資格情報を提供し、提供、アクセス トークンのスコープ内のテナントのヒントを次のようにします。
3. セキュリティ上の理由または秘密の侵害の場合に、患者アプリケーション シークレットを再生成しを無効にしたり削除したりできます (同じ例は、Azure ポータルの AAD アプリケーションの登録で利用可能な) 古いシークレット
4. 適合に関する声明をホストしているメタデータのエンドポイントは thenticated を解除する必要があります、認証トークンにアクセス可能な場合があります。
5. パートナー サービスは、クライアント資格情報のフローを使用してアクセス トークンを要求する患者のアプリケーションのトークンのエンドポイントを提供します。 承認サーバーにトークンの url は、この例のように FHIR サーバー上のメタデータのフェッチ、FHIR 準拠 (機能) のステートメントの一部にする必要があります。

![患者アプリ 5](../../media/Patient-app-5.png)

アクセス トークンの要求は、次のパラメーターで構成されます。

    POST /token HTTP/1.1
    Host: authorization-server.com

    grant-type=client_credentials
    &client_id=xxxxxxxxxx
    &client_secret=xxxxxxxxxx

パートナー サービスは、患者のアプリケーション、パートナーの側での認証登録ポータルを介して管理の client_id と client_secret を提供します。 パートナー サービスは、クライアント資格情報のフローを使用して要求のアクセス トークンにエンドポイントを提供します。 正常な応答は、token_type、access_token および expires_in パラメーターを含める必要があります。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>プロバイダー エンドポイントにマッピング AAD テナントをルーティングします。

患者のアプリケーションは、1 つのエンドポイントを介してパートナー サービスに接続します。 パートナー サービスが所有し、パートナーのサービスを使用する各医療機関 (FHIR サーバー) に各 Microsoft 顧客 (AAD テナント ID) をマップするためのメカニズムを維持します。

AAD テナントをプロバイダー エンドポイントにマッピングすると、AAD テナント ID (GUID) が使用します。 患者のアプリケーションは、要求ごとにアクセス トークンを要求しているときに、スコープ内のテナント ID を渡します。 パートナー サービスは、プロバイダー エンドポイントへのテナント ID へのマッピングを保持し、テナント ID に基づいて、プロバイダー エンドポイントに要求をリダイレクト これを行うには、(手動でまたはのプロバイダー組織は、相互運用機能のプラットフォームの一部としてポータルを経由して)、パートナーは、最後の構成をサポートします。

認証およびルーティングのワークフローを次に示します。

![患者アプリ 6](../../media/Patient-app-6.png)

1. 送信することによってアプリケーションのアクセス トークンを要求します。
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. アプリケーション トークンで応答します。

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. アクセス トークンを使用して保護されたデータを要求します。
4. 承認メッセージ: サーバーを選択して、適切な FHIR のスコープ内のテナント ID へのルーティング
5. アプリケーション トークンを認証した後、FHIR サーバーを承認されたから保護されているアプリケーション データを送信します。

## <a name="interfaces"></a>インタ フェース

特定の呼び出しと患者のアプリケーションで使用されるフィールドは、次の資料に記載されています。 FHIR サーバーと FHIR の Api に該当するインターフェイスを選択します。

- [DSTU2 インターフェイスの仕様](dstu2-interface.md)
- [STU3 インターフェイスの仕様](stu3-interface.md)

## <a name="performance-and-reliability"></a>パフォーマンスと信頼性

患者のアプリケーションは、プライベートのプレビュー中は、エンド ・ ツー ・ エンドのパフォーマンスの保証はありません。 パフォーマンスの要因には、相互運用機能のパートナー ・ ヘルス ・ システムの環境では、EHR の開始、ワークフローに関連するすべてのホップの相対遅延時間が含まれますと、インフラストラクチャ、FHIR サーバーを含む、で Office 365 のエコシステムにし、。患者のアプリケーションです。

![相互運用パートナー](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR を開始します。  

FHIR にマイクロソフト チームの EHR の統合インターフェイスを公開することができます FHIR サーバーに簡単にアクセスすると、マイクロソフトではオープン ソースの FHIR サーバーが使用するすべての開発者向けに用意します。 FHIR サーバーが Microsoft から利用可能なオープン ・ ソースの詳細について、組織の展開と[Azure の FHIR サーバーは、どのような](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)資料を参照してください。

環境を使用できます、HSPC を開くサンド ボックス EHR を作成するにも、開いている FHIR サーバーをサポートし、これを使用して患者のアプリで遊んでいる、EHR。 [HSPC のサンド ボックスのマニュアル](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)を読むことをお勧めします。 だけでなく、サンド ボックスを提供して、簡単に、UI 指向であり、作成、追加、および患者の編集、ユーザー フレンドリな方法も提供を開始するいくつかのサンプルです。  

## <a name="enroll-in-the-private-preview"></a>プライベート プレビューに登録します。

FHIR サーバーのソースを開く、作成した後は、以下に説明する手順を実行して、テナント内の患者のアプリケーションに接続するのには実に簡単です。

1. 次の最初の詳細の[お問い合わせ](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview):  
    - お名前 * 
    - 自分の位置 
    - 会社または組織を表す
    - EHR の統合のための患者のアプリに興味のある理由です。 

    戻るをできるだけ早くその他の質問で、プライベート プレビューの設定を取得するプロセスについて説明しては。

2. カスタムを sideloading ことを確認どこに患者のアプリを試すテナントでアプリケーションを有効にします。 [アプリケーションのアクセス許可ポリシー](../../admin-settings.md)を有効にするチームの管理センターから、または、お客様のテナントの方法についてを参照してください。

3. Sideload 患者のアプリケーション マニフェストはから入手することマイクロソフト (後に、電子メールの処理) に注意を払って調整と患者の丸めのシナリオに使用するテナントのチームに。 側アプリケーションをロードする方法の詳細については[マイクロソフトのチームに、アプリケーション パッケージをアップロードするの](/microsoftteams/platform/concepts/apps/apps-upload)には

4. チームの所有者は、一般的なチャネルに移動し、[患者] タブをクリックします。EHR モードと手動モードの 2 つを提供する最初の実行エクスペリエンス オプションなどが表示されます。 **EHR のモード**を選択し、エンドポイントをコピー、FHIR サーバー (以前のバージョンに、すべての必要なデータと仕様上あたりのリソースだけでセットアップした結果)、[リンク] フィールドに、接続にも、FHIR サーバーを表す名前を付けてしてください。 接続] をクリックし、移動する準備がすべて必要があります。

    ![患者のアプリケーション サーバーの設定](../../media/patients-server.png)

5. 検索してから、FHIR サーバー/EHR の患者のリストに追加し、何かが機能しない場合、[フィードバック](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)をしてください、アプリケーションを使用して起動します。 また、患者のアプリケーションの完全に認証されたバージョンを確立するために-_gt FHIR サーバーの流れ、相談してくださいを通じて医療の製品がエンジニア リング用には、マイクロソフトのチームでオフライン ダイアログ ボックスで電子メールの要求が前述の要件を明確にすると、我々 は。これを有効にする FHIR インターフェイスのドキュメントで説明した認証要件を支援します。  


