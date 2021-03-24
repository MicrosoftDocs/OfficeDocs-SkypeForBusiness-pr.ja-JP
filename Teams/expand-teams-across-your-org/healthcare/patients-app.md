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
description: FHIR API を使用して、電子医療記録を Microsoft Teams 患者アプリに統合する方法について説明します。
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

この記事は、医療情報システムの上で FHIR API を使用して Microsoft Teams に接続することに関心がある一般的な医療 IT 開発者を対象としています。 これにより、医療組織のニーズに合ったケア協調シナリオが可能になります。

リンクされた記事では、Microsoft Teams Patients アプリの FHIR インターフェイス仕様について説明し、次のセクションでは、FHIR サーバーをセットアップし、開発環境またはテナントの患者アプリに接続するために必要な理由について説明します。 また、選択した FHIR サーバーのドキュメントを理解する必要があります。これは、サポートされているオプションの 1 つである必要があります。

- Datica [(CMI](https://datica.com/compliant-managed-integration/) サービスを通じて)
- Infor Cloverleaf [(Infor FHIR Bridge を通る](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- Redox [(R^FHIR サーバー経由](https://www.redoxengine.com/fhir/))
- Dapasoft [(FHIR の場合は、](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> このプロセスには、Microsoft Teams 管理センターまたは PowerShell コマンドレットを使用して機能を有効にする手順は含まれています。 構成は、FHIR サーバー/サービス側と患者アプリ クライアントで完全に行われます。

次に示すのは、患者アプリのアーキテクチャです。

![患者アプリのアーキテクチャの図](../../media/patients-app-architecture.png)

次のセクションでは、患者アプリと統合するために FHIR サーバー (または EHR で FHIR API を有効にする) が満たす必要がある、患者アプリの FHIR 専用データ アクセスレイヤーの要件について説明します。

- ユーザー認証に関する期待
- 統合インターフェイスの機能要件と技術的要件
- パフォーマンスと信頼性に関する期待
- 患者アプリでサポートされる FHIR リソースに関する期待
- 統合プロセスと期待される契約モデル
- FHIR の使用を開始する方法と、患者アプリで直面する一般的な課題
- 患者アプリの次の反復に関する将来の要件

> [!NOTE]
> 次のセクションでは、"partner" または "Interop partner" という単語は、FHIR を介して患者アプリの EHR システムに統合できるサードパーティ組織を参照するために使用され、記載されている仕様に合わせて FHIR Server を実装しています。

## <a name="functional-and-technical-requirements"></a>機能要件と技術要件  

### <a name="authentication"></a>認証  

ユーザー レベルの承認がサポートされなくても、ユーザー レベルの承認をサポートするアプリ レベルの承認は、EHR システムがユーザー レベルの承認を実装している場合でも、FHIR を通じてデータ変換を実行し、EHR データへの接続を公開する、より一般的にサポートされている方法です。 相互運用サービス (パートナー) は EHR データへのアクセスを昇格し、適切な FHIR リソースと同じデータを公開すると、相互運用サービスまたはプラットフォームと統合された Interop Service Consumer (The Patients アプリ) に渡される承認コンテキストはありません。 患者アプリはユーザー レベルの承認を強制できますが、患者アプリと相互運用パートナーのサービス間のアプリケーション認証をサポートします。

アプリケーション間認証モデルの説明を以下に示します。

サービス間認証は、OAuth 2.0 クライアント資格情報フロー [を通じて行う必要があります](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)。 パートナー サービスは、次の情報を提供する必要があります。

1. パートナー サービスを使用すると、患者アプリがパートナーとアカウントを作成できます。これにより、患者アプリはパートナーの認証サーバーの認証登録ポータルを介して管理される client_id と client_secret を生成して所有することができます。

2. パートナー サービスは認証/承認システムを所有します。このシステムは、提供されたクライアント資格情報を受け入れて検証 (認証) し、次に示すスコープでテナントヒントを含むアクセス トークンを返します。

3. セキュリティ上の理由から、または秘密違反が発生した場合、患者アプリは秘密を再生成し、古い秘密を無効化または削除することができます (同じ例は Azure Portal で利用できます - AAD アプリ登録)。

4. 準拠ステートメントをホストするメタデータ エンドポイントは認証されていない必要があります。認証トークンなしでアクセスできる必要があります。

5. パートナー サービスは、患者アプリのトークン エンドポイントを提供し、クライアント資格情報フローを使用してアクセス トークンを要求します。 承認サーバーごとのトークン URL は、次の例のように FHIR サーバー上のメタデータからフェッチされる FHIR 準拠 (機能) ステートメントの一部である必要があります。

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

パートナー サービスは、パートナー client_id認証client_secret認証登録ポータルを介して管理される患者用アプリの機能を提供します。 パートナー サービスは、クライアント資格情報フローを使用してアクセス トークンを要求するエンドポイントを提供します。 正常に応答するには、パラメーター token_type、access_token、expires_inする必要があります。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>ルーティング: AAD テナントをプロバイダー エンドポイントにマッピングする

患者アプリは、単一のエンドポイントを介してパートナー サービスに接続します。 パートナー サービスは、各 Microsoft 顧客 (AAD テナント ID) をパートナー サービスが動作している各医療プロバイダー (FHIR サーバー) にマップするメカニズムを所有し、維持します。

AAD テナントをプロバイダー エンドポイントにマッピングするには、AAD テナント ID (GUID) が使用されます。 患者アプリは、要求ごとにアクセス トークンを要求しながら、スコープ内のテナント ID を渡します。 パートナー サービスは、テナント ID のプロバイダー エンドポイントへのマッピングを保持し、テナント ID に基づいて要求をプロバイダー エンドポイントにリダイレクトします。 これを行うには、パートナーはエンドで構成をサポートします (プロバイダー組織の相互運用プラットフォームへのオンボーディングの一環として、手動で、またはポータル経由で行います)。

認証とルーティングのワークフローを次に示します。

![認証とルーティングのワークフローの図](../../media/Patient-app-6.png)

1. 送信によるアプリ アクセス トークンの要求:
 
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

3. Access トークンを使用して保護されたデータを要求します。

4. 承認メッセージ: スコープ内のテナント ID からルーティングする適切な FHIR サーバーを選択します。

5. アプリ トークンで認証した後、承認された FHIR サーバーからアプリで保護されたデータを送信します。

## <a name="interfaces"></a>インターフェイス

患者アプリで使用される特定の呼び出しとフィールドは、次の記事に記載されています。 FHIR サーバー/FHIR API に該当するインターフェイスを選択します。

- [DSTU2 インターフェイスの仕様](dstu2-interface.md)
- [STU3 インターフェイスの仕様](stu3-interface.md)

## <a name="performance-and-reliability"></a>パフォーマンスと信頼性

患者アプリがプライベート プレビューに表示されている間、エンドツーエンドのパフォーマンスに保証はありません。 パフォーマンスの要因には、正常性システムの環境での EHR から、FHIR Server や Office 365 エコシステムや患者アプリを含む相互運用パートナーとそのインフラストラクチャへの、ワークフローに関係するすべてのホップの相対的な遅延が含まれます。

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR の使用を開始する  

FHIR を使い始め、Microsoft Teams EHR 統合インターフェイスに公開できる FHIR サーバーに簡単にアクセスする必要がある場合、Microsoft には、すべての開発者が使用できるオープン ソースの FHIR サーバーがあります。 Microsoft から利用可能なオープン ソースの FHIR Server の詳細 [については、「FHIR Server for Azure](/azure/healthcare-apis/overview-open-source-server) とは何か」の記事を参照し、組織に展開してください。

HSPC Open Sandbox EHR 環境を使用して EHR を作成することもできます。EHR は開いている FHIR サーバーもサポートし、これを使用して患者アプリで遊び回ります。 HSPC サンドボックスのドキュメント [を参照することをお勧めします](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)。 サンドボックスは、患者の作成、追加、編集を簡単に行える UI 指向のユーザー向けの方法を提供するだけでなく、使用を開始するためのいくつかのサンプルも提供します。