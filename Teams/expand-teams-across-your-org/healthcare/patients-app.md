---
title: 患者アプリの概要
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: FHIR API を使用して、電子医療記録を Microsoft Teams患者アプリに統合する方法について説明します。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096211"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>電子医療記録を Microsoft Teams に統合する

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

この記事は、医療情報システムの上で FHIR API を使用して医療情報システムに接続することに関心がある一般的な医療 IT 開発者を対象Microsoft Teams。 これにより、医療組織のニーズに合ったケア調整シナリオが可能になります。

リンクされた記事では、Microsoft Teams Patients アプリの FHIR インターフェイス仕様について説明し、以下のセクションでは、FHIR サーバーを設定し、開発環境またはテナント内の Patients アプリに接続するために必要な内容について説明します。 また、選択した FHIR サーバーのドキュメントを理解する必要があります。これは、サポートされているオプションの 1 つである必要があります。

- Datica [(CMI](https://datica.com/compliant-managed-integration/) オファリングを通じて)
- Infor Cloverleaf [(Infor FHIR ブリッジ経由](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox [(R^FHIR サーバー経由](https://www.redoxengine.com/fhir/))
- Dapasoft [(FHIR の Corolar 経由](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> このプロセスには、管理センターまたは PowerShell コマンドレットMicrosoft Teams機能を有効にする手順は含まれています。 構成は、FHIR サーバー/サービス側と Patients アプリ クライアントで完全に行われます。

次に示すのは、Patients アプリのアーキテクチャです。

![Patients アプリのアーキテクチャの図](../../media/patients-app-architecture.png)

次のセクションでは、次のような、FHIR サーバー (または EHR 対応 FHIR API) が Patients アプリと統合するために満たす必要がある、Patients アプリの FHIR 専用データ アクセス 層の要件について説明します。

- ユーザー認証に関する期待
- 統合インターフェイスの機能要件と技術要件
- パフォーマンスと信頼性に関する期待
- Patients アプリでサポートされる FHIR リソースに関する期待
- 統合プロセスと予想されるエンゲージメント モデル
- FHIR の使用を開始する方法と、Patients アプリで直面する一般的な課題
- Patients アプリの次のイテレーションに関する将来の要件

> [!NOTE]
> 次のセクションでは、"partner" または "Interop partner" という単語は、FHIR を介して Patients アプリの EHR システムへの統合を可能にし、記載されている仕様に合わせて FHIR Server を実装しているサードパーティの組織を参照するために使用されます。

## <a name="functional-and-technical-requirements"></a>機能要件と技術要件  

### <a name="authentication"></a>認証  

ユーザー レベルの承認をサポートするアプリ レベルの承認は、EHR システムがユーザー レベルの承認を実装している場合でも、FHIR を介してデータ変換を実行し、EHR データへの接続を公開する、より一般的にサポートされる方法です。 Interop Service (パートナー) は EHR データへの昇格されたアクセス権を取得し、適切な FHIR リソースと同じデータを公開すると、Interop Service または Platform と統合された Interop Service Consumer (Patients アプリ) に渡される承認コンテキストはありません。 Patients アプリはユーザー レベルの承認を強制できますが、Patients アプリと Interop パートナーのサービス間のアプリケーション認証をサポートします。

アプリケーション間認証モデルの説明は次のとおりです。

サービス間認証は、OAuth 2.0 クライアント資格情報フロー [を通じて行う必要があります](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 パートナー サービスは、次の情報を提供する必要があります。

1. パートナー サービスを使用すると、Patients アプリはパートナーとアカウントを作成できます。これにより、Patients アプリはパートナーの認証サーバーの認証登録ポータルを使用して管理する client_id と client_secret を生成して所有できます。

2. パートナー サービスは認証/承認システムを所有しています。このシステムは、指定されたクライアント資格情報を受け入れて検証 (認証) し、次に示すテナント ヒントをスコープに含むアクセス トークンを返します。

3. セキュリティ上の理由から、またはシークレット違反が発生した場合、Patients アプリはシークレットを再生成し、古いシークレットを無効化または削除できます (同じ例は、Azure Portal - AAD アプリ登録で利用できます)。

4. 準拠ステートメントをホストするメタデータ エンドポイントは認証されていない必要があります。認証トークンなしでアクセスできる必要があります。

5. パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求する、Patients アプリのトークン エンドポイントを提供します。 承認サーバーごとのトークン URL は、次の例のように、FHIR サーバーのメタデータからフェッチされた FHIR 準拠 (機能) ステートメントの一部である必要があります。

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

アクセス トークンの要求は、次のパラメーターで構成されます。

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

パートナー サービスは、パートナー側client_id認証client_secretポータルを使用して管理される、Patients アプリのアプリケーションとサービスを提供します。 パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求するエンドポイントを提供します。 成功した応答には、token_type パラメーター、access_tokenパラメーター expires_inがあります。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>ルーティング: AAD テナントをプロバイダー エンドポイントにマッピングする

Patients アプリは、1 つのエンドポイントを介してパートナー サービスに接続します。 パートナー サービスは、各 Microsoft 顧客 (AAD テナント ID) を、パートナー サービスが操作しているそれぞれの医療プロバイダー (FHIR サーバー) にマップするメカニズムを所有および管理します。

AAD テナントをプロバイダー エンドポイントにマッピングするには、AAD テナント ID (GUID) を使用します。 Patients アプリは、要求ごとにアクセス トークンを要求しながら、スコープ内のテナント ID を渡します。 パートナー サービスは、テナント ID のプロバイダー エンドポイントへのマッピングを保持し、テナント ID に基づいて要求をプロバイダー エンドポイントにリダイレクトします。 これを行うには、パートナーはエンドで構成をサポートします (プロバイダー組織の Interop Platform へのオンボードの一環として、手動またはポータルを使用)。

認証とルーティングのワークフローを次に示します。

![認証とルーティングのワークフローの図](../../media/Patient-app-6.png)

1. 次を送信してアプリ アクセス トークンを要求します。
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. アプリ トークンで返信する:

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. アクセス トークンを使用して保護されたデータを要求します。

4. 承認メッセージ: スコープ内のテナント ID からにルーティングする適切な FHIR サーバーを選択します。

5. アプリ トークンで認証した後、承認された FHIR サーバーからアプリで保護されたデータを送信します。

## <a name="interfaces"></a>インターフェイス

Patients アプリで使用される特定の呼び出しとフィールドについては、次の記事を参照してください。 FHIR サーバー/FHIR API に適用可能なインターフェイスを選択します。

- [DSTU2 インターフェイスの仕様](dstu2-interface.md)
- [STU3 インターフェイスの仕様](stu3-interface.md)

## <a name="performance-and-reliability"></a>パフォーマンスと信頼性

Patients アプリはプライベート プレビュー中ですが、エンド to エンドのパフォーマンスに関する保証はありません。 パフォーマンスの要因には、正常性システムの環境内の EHR から、Interop パートナーとそのインフラストラクチャ (FHIR Server を含む)、および Office 365 エコシステムおよび Patients アプリまで、ワークフローに関連するすべてのホップの相対的な待機時間が含まれます。

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR の使用  

FHIR を使い始め、Microsoft Teams EHR 統合インターフェイスに公開できる FHIR Server に簡単にアクセスする必要がある場合、Microsoft には、すべての開発者が使用できるオープン ソースの FHIR Server があります。 Microsoft から提供 [されているオープン ソースの FHIR Server](/azure/healthcare-apis/overview-open-source-server) の詳細と組織向けデプロイについては、「Azure の FHIR Server とは」を参照してください。

HSPC Open Sandbox EHR 環境を使用して、開いている FHIR サーバーもサポートする EHR を作成し、これを使用して Patients アプリを使用することもできます。 HSPC Sandbox のドキュメント [を参照することをお勧めします](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 サンドボックスでは、患者の作成、追加、編集を簡単で UI 指向でユーザーにわかりやすい方法で行えるだけでなく、使用を開始するためのサンプルもいくつか用意されています。