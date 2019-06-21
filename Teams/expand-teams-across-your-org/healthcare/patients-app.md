---
title: Patients アプリの概要
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
description: Microsoft Teams の患者向けアプリ EHR の統合
ms.openlocfilehash: b76dd4d721d934b4597c5faf1a8f2fc739d5281d
ms.sourcegitcommit: 1786d4beccc8749e20709d2360d90e2bf7634925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "35115994"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>電子医療記録を Microsoft Teams に統合する

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

プライベートプレビューに参加するには、「[プライベートプレビューに登録](#enroll-in-the-private-preview)する」を参照してください。

この記事は、医療情報システム上で FHIR Api を使用して Microsoft Teams に接続することに関心を持っている一般的なヘルスケアの IT 開発者を対象としています。 これにより、医療機関のニーズに合ったケアの調整シナリオが可能になります。

リンクされた記事ドキュメント「Microsoft Teams の患者」アプリの FHIR インターフェイスの仕様について説明し、以降のセクションでは、FHIR サーバーの設定と開発環境またはテナントでの患者アプリへの接続に必要なものについて説明します。 また、選択した FHIR サーバーのドキュメントについて理解している必要があります。これは、サポートされているオプションのいずれかである必要があります。
- Datica ( [CMI](https://datica.com/compliant-managed-integration/)サービス経由)
- Infor Cloverleaf ( [Infor FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)経由)
- Redox ( [r ^ FHIR サーバ](https://www.redoxengine.com/fhir/)を経由)
- Dapasoft (の場合は、 [FHIR の](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)場合)

> [!NOTE]
> このプロセスには、Microsoft Teams 管理センターまたは PowerShell コマンドレットを使用して機能を有効にする手順は含まれていません。 構成は、FHIR サーバー/サービス側と患者のアプリクライアントで行われます。

次に、患者アプリのアーキテクチャを示します。

![患者のアプリアーキテクチャの図](../../media/patients-app-architecture.png)

以下のセクションでは、患者アプリと統合するために、FHIR server (または EHR が有効な FHIR Api) が満たす必要のある、FHIR 専用データアクセスレイヤーの要件について説明します。これには、次のものが含まれます。

- ユーザー認証に関する期待
- 統合インターフェイスの機能と技術の要件
- パフォーマンスと信頼性に関する期待
- 患者アプリでサポートされる FHIR リソースに対する期待
- 統合のプロセスと想定される契約モデル
- 患者アプリのプライベートプレビューで自分と顧客を登録する方法
- FHIR の使用を開始する方法と、患者アプリで直面する一般的な課題
- 患者アプリの次回のイテレーションに関する将来の要件

> [!NOTE]
> 以下のセクションでは、"パートナー" または "相互運用パートナー" という単語を使用して、患者アプリの EHR システムと FHIR の統合を可能にするサードパーティ組織を参照しています。また、リストされている仕様に合わせて FHIR サーバーが実装されています。

## <a name="functional-and-technical-requirements"></a>機能と技術の要件  

### <a name="authentication"></a>認証  

*ユーザーレベルの承認をサポートしていない*アプリレベルの承認は、ehr システムでユーザーレベルの承認が実装されている場合でも、データ変換を実行し、ehr データへの接続を公開するための、より一般的にサポートされている方法です。. 相互運用サービス (パートナー) は、EHR データへのアクセス権を昇格させ、そのデータを適切な FHIR リソースとして公開すると、相互運用サービスコンシューマー (患者アプリ) に対して認証コンテキストが渡されることはありません。サービスまたはプラットフォーム。 患者のアプリでは、ユーザーレベルの承認を強制することはできませんが、患者のアプリと相互運用パートナーのサービス間でのアプリケーションの認証をサポートしています。

アプリケーション間のアプリケーション認証モデルについては、次の説明を参照してください。

サービス間認証は、OAuth 2.0[クライアントの資格情報フロー](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)を通じて実行する必要があります。 パートナーサービスは、次の情報を提供する必要があります。

1. パートナーサービスは、患者アプリがパートナーとのアカウントを作成できるようにします。これにより、患者アプリは、パートナーの認証サーバー上の認証登録ポータルを通じて管理される client_id と client_secret を生成し、所有することができます。
2. パートナーサービスは、次に示すように、提供された認証/承認システムを所有しており、指定されたクライアントの資格情報を受け入れて検証 (認証) し、テナントヒントを含むアクセストークンを返します。
3. セキュリティ上の理由により、または秘密の違反が発生した場合、患者アプリは秘密を再生成し、古いシークレットを無効化または削除することができます (例: Azure Portal で利用可能な場合)。
4. 準拠ステートメントをホストしているメタデータエンドポイントは、認証トークンなしでアクセスできる必要があります。
5. パートナーサービスは、患者アプリのトークンエンドポイントを提供し、クライアントの資格情報フローを使ってアクセストークンを要求します。 次の例のように、認証サーバーごとのトークン url は、FHIR サーバーのメタデータから取得された、FHIR 準拠 (機能) ステートメントの一部である必要があります。

* * *
    {"resourceType": "CapabilityStatement"。
        .
        .
        "rest": [{"mode": "server"、"security": {"extension": [{"extension": [{"url": "token", "valueuri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" "、" valueurihttps://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorizehttp://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris":" "、" "という url": ""、"" のように入力してください: "" {"" {"" "と"http://hl7.org/fhir/ValueSet/restful-security-service"{" "]} ] } ] }, .
                .
                .
            } ] }

* * *

アクセストークンの要求は、次のパラメーターで構成されます。

* * *

    POST/token HTTP/1.1 Host: authorization-server.com

    grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx

* * *

パートナーサービスは、パートナーの側の認証登録ポータルで管理されている、client_id と client_secret の患者アプリを提供します。 パートナーサービスは、クライアントの資格情報フローを使用してアクセストークンを要求するエンドポイントを提供します。 成功応答には、token_type、access_token、expires_in の各パラメーターが含まれている必要があります。

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>ルーティング: のプロバイダーエンドポイントへの AAD テナントのマッピング

患者アプリは、1つのエンドポイントを通じてパートナーサービスに接続します。 パートナーサービスは、パートナーサービスが作業している各 Microsoft 顧客 (AAD テナント ID) をそれぞれの医療機関 (FHIR サーバー) にマップするメカニズムを所有し、管理します。

AAD テナントをプロバイダーエンドポイントにマッピングすると、AAD テナント ID (GUID) が使用されます。 患者アプリは、各要求のアクセストークンを要求しながら、スコープ内でテナント ID を渡します。 パートナーサービスは、テナント id とプロバイダーエンドポイントのマッピングを維持し、テナント ID に基づいて要求をプロバイダーエンドポイントにリダイレクトします。 これを行うには、パートナーがエンドでの構成を (手動で、または、プロバイダ組織のオンボードから相互運用プラットフォームへの入り口の一部として) サポートします。

認証とルーティングのワークフローは、次のようになります。

![認証とルーティングワークフローの図](../../media/Patient-app-6.png)

1. 送信することにより、アプリアクセストークンを要求します。
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. アプリトークンを使って返信する:

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. アクセストークンを使用して、保護されたデータを要求します。
4. 承認メッセージ: 範囲内のテナント ID から適切な FHIR サーバーを選択してルーティングする
5. アプリトークンを使って認証した後、承認された FHIR サーバーからアプリの保護されたデータを送信します。

## <a name="interfaces"></a>インターフェイス

患者アプリで使用される特定の通話とフィールドについては、次の記事で説明します。 FHIR サーバー/FHIR Api に適用可能なインターフェイスを選択します。

- [DSTU2 インターフェイスの仕様](dstu2-interface.md)
- [STU3 インターフェイスの仕様](stu3-interface.md)

## <a name="performance-and-reliability"></a>パフォーマンスと信頼性

患者のアプリはプライベートプレビュー版ですが、エンドツーエンドのパフォーマンスに保証はありません。 パフォーマンスの要因としては、正常性システムの環境内の EHR から、相互運用性パートナーとそのインフラストラクチャ (FHIR サーバーを含む)、および Office 365 エコシステムを含む、ワークフローに関連するすべてのホップの相対的な待ち時間が含まれます。患者アプリ。

![相互運用パートナーのパフォーマンスの図](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>FHIR の使用を開始する  

FHIR を初めて使用して、Microsoft Teams の EHR 統合インターフェイスに公開できる FHIR サーバーに簡単にアクセスする必要がある場合は、Microsoft によって、すべての開発者が使用できるオープンソース FHIR サーバーが用意されています。 Microsoft から提供されているオープンソース FHIR サーバーの詳細については、「 [Azure 用 FHIR サーバーとは](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server)」の記事を参照してください。

HSPC オープンサンドボックス EHR 環境を使用して、オープンな FHIR サーバーもサポートしている EHR を作成し、これを使って患者のアプリでプレイすることもできます。 [Hspc サンドボックスのドキュメント](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)をご覧になることをお勧めします。 サンドボックスは、簡単で UI 指向であり、患者の作成、追加、編集を行うためのわかりやすい方法を提供するだけでなく、使用を開始するためのサンプルもいくつか提供しています。  

## <a name="enroll-in-the-private-preview"></a>プライベートプレビューに登録する

オープンソース FHIR サーバーを作成した後は、次の手順に従って、テナント内の患者アプリに簡単に接続できます。

1. 以下の最初の詳細をご確認[ください](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview)。  
    - お名前 *
    - 自分の位置
    - 代表する会社または組織
    - EHR との統合のための患者アプリに関心を持っている理由

    さらに多くの質問がある場合は、すぐにお客様にご連絡いたします。また、プライベートプレビュー用にセットアップする手順についてもご案内します。

2. 患者のアプリを試すテナントで、カスタムアプリのサイドローディングが有効になっていることを確認します。 この機能を Teams 管理センターからお客様のテナントに対して有効にする方法については、「[アプリのアクセス許可ポリシー](../../admin-settings.md) 」を参照してください。

3. サイドローディングは、ケアと患者の丸めのシナリオで使用されるテナント内のチームに、Microsoft から取得する患者のアプリマニフェストを示しています (メールを処理した後)。 アプリのサイドロードの詳細な手順については、「[アプリパッケージを Microsoft Teams にアップロード](/microsoftteams/platform/concepts/apps/apps-upload)する」をご覧ください。

4. チーム所有者として [全般] チャネルに移動し、[患者] タブをクリックします。次に、EHR モードと手動モードの2つのオプションが表示される最初の実行環境が表示されます。 [EHR]**モード**を選び、Fhir サーバーのエンドポイント (前述の仕様に含まれているすべての必要なデータとリソースが前に設定されています) を Link フィールドにコピーして、その接続に FHIR サーバーを表す名前を付けてください。 [接続] をクリックすると、すべての機能を使い始めることができます。

    ![患者のアプリのサーバー設定のスクリーンショット](../../media/patients-server.png)

5. このアプリを使って FHIR サーバー/EHR から患者を検索し、それをリストに追加して、問題が解決しない場合は[フィードバック](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback)を送信してください。 また、完全に認証されたバージョンの患者 > アプリを確立するには、「医療製品エンジニアリング用の Microsoft Teams を使用して、オフラインで作業する」を参照してください。これについては、前に説明したメールリクエストに従って、必要条件を明確化してください。この機能を有効にするには、FHIR インターフェイスドキュメントで説明した認証要件に従ってください。  


