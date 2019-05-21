---
title: 医療関係組織のためのTeamsを始めましょう
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 医療関係組織のためのTeamsを始めましょう
ms.openlocfilehash: 40eccf379af8c0acd318cb3a8b1b647357f6cf7c
ms.sourcegitcommit: a46dad8dfc685534d81bb011f3c099c6f59ce2e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "33882894"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>医療関係組織のためのTeamsを始めましょう

Microsoft Teams には、病院およびその他の医療機関向けの便利な機能が数多く用意されています。 Teams の機能は、次の機能を利用して、病院を支援します。

- ケアの調整と共同作業
- セキュリティで保護されたメッセージング
- テレの健康
- 電子医療記録 (EHR) の統合 
- Firstline Worker システムの統合 

これは、Microsoft Teams の基本機能 (会議、通話、メッセージングなど) に加えています。 

## <a name="care-coordination---microsoft-teams-patients-app"></a>ケアの調整-Microsoft Teams の患者アプリ

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams には、医療機関向けの優れた調整ソリューションが用意されました。これにより、患者の治療を最大限に活用できるようになります。 医療調整ソリューションの crux、Microsoft Teams の患者アプリは、高速な医療相互運用性リソース ([Fhir](https://www.hl7.org/fhir/)) インターフェイスを使って、ehr (電子医療記録) システムと統合された、初めてのパーティタブアプリです。臨床的な共同作業とコミュニケーションを可能にするために、Microsoft Teams の医療情報を利用できます。  

治療の調整ソリューションは、HL7v2 や FHIR などの既存の正常性データ標準を使用して、患者のアプリを EHR システムに接続できる、主要な独立系ソフトウェアベンダー (Isv) とのインターフェイスを作成できます。 Microsoft パートナーは、次の業界のリーダーと協力して、チームとの電子的医療記録の統合を確立しています。

- Datica ( [CMI](https://datica.com/compliant-managed-integration/)サービス経由)
- Infor Cloverleaf ( [Infor FHIR ブリッジ](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)経由)
- Redox ( [r ^ FHIR サーバ](https://www.redoxengine.com/fhir/)を経由)
- Dapasoft (の場合は、 [FHIR の](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)場合)

医療機関向けの Microsoft Teams を実装しようとして、EHR との相互運用パートナーが、医療機関の組織の EHR システムとの安全で認証された接続を患者アプリに提供する必要があります。 これにより、関連する患者レコードの一方向 (読み取り専用) を患者のアプリに転送できます。 患者アプリは FHIR 形式を理解しているため、パートナーも、HL7v2 などのさまざまな形式から集約されたデータを FHIR DSTU2 または STU3 に変換する責任を負います。

<br>

![EHR との統合](../../media/ehr-1.png)

<br>

患者アプリは、EHR (電子医療記録) システムと統合され、医療機関がチームのセキュリティで保護されたプラットフォーム内でリアルタイムで患者の治療を伝えることができます。 患者アプリは、次の課題に対処することを目的とした、治療の調整分野における最初の大きな投資です。

- 患者の体験を通じて、即座に、または重要なコミュニケーションを低効率で行う
- 管理の負担を作る孤立情報
- 複雑で断片化されたコラボレーションツールを使用した clinicians 間の不満
- 低コストの臨床時間の増加に対応する、非効率的な相手の治療の調整

Microsoft Teams を使用すると、医師、clinicians、看護師、および他のスタッフが効率的に共同作業を行うことができます。

- Office ドキュメントの操作と共同作業を行う単一の仮想化されたチームの一員である
- 注意が必要な患者についての常設の会話
- 作業を構造化するための手段としてタブでチャネルを使用し、情報ソースをピン留めできるタブから追加のヘルプを表示する
- チームの音声、ビデオ、画面共有、録音、および議事録機能を活用して、毎日の会議を管理するためのチャネル会議の使用
- 患者アプリを使って、監視する必要があるハイリスク患者のリストを取得し、EHR システムから最新の詳細情報を取得します。 患者アプリ自体には、Microsoft Teams の次の機能が追加されています。

    - 1つのチャネル内に複数の患者リストを作成することができます。
    - 構成可能な列を使用して、患者について表示される情報を表示して並べ替えることができます。
    - チームテンプレートを使用してアプリを自動プロビジョニングする機能。
    - IOS および Android 用の Teams アプリで、モバイルの第1のヘルスケアワーカーおよび Microsoft Teams web とデスクトップクライアント用に利用できます。
    - 準拠ステートメントの解析による FHIR DSTU2 と STU3 のバージョンのサポート。
    - ユーザーインターフェイス上のすべてのビューと検索操作の監査ログを使用して、HIPAA ガイドラインごとに PHI を保護します。

患者アプリは Teams の拡張性プラットフォームに基づいて構築されており、タブフレームワークを利用して、チャネル内に豊富な患者コンテンツを表示します。 他の Teams アプリとプラットフォーム自体の詳細については、「 [Microsoft teams 用アプリ](/microsoftteams/platform/concepts/apps/apps-overview)」を参照してください。  

> [!NOTE]
> 患者アプリはプライベートプレビューであり、FHIR インターフェイスはベータ版です。 リリースされたバージョンは、下位互換性が期待されるとは限りません。

![患者のアプリのスクリーンショット](../../media/ehr-2.png)

「[電子医療レコードを Microsoft Teams に統合](patients-app.md)して実装の詳細を確認する」を参照してください。

## <a name="templates"></a>Templates

Teams を作成するための新しいテンプレートは、病院の設定に適用するために開発されたもので、近日中に対応する予定です。 これにより、医療員がさまざまな部署または wards の患者の注意を調整するために使用するチームの作成が容易になります。 「[医療機関向けのチームテンプレートの概要](healthcare-templates.md)」を参照してください。 Cardiology、またはケア wards などの社内部署向けにチームを開始したり、その他のテンプレートを開発中に追加したりすることができます。

## <a name="secure-messaging"></a>セキュリティで保護されたメッセージング

セキュリティで保護されたメッセージングは、いくつかの新機能を含む、ケアチーム内の共同作業をサポートします。

- メッセージの送信者は、メッセージに特別な優先順位を設定できます。そのため、受信者は、メッセージが読み上げられるまで、受信者に対して繰り返し通知されます。
- メッセージの送信者は、開封確認メッセージを要求できます。そのため、送信したメッセージがメッセージの受信者によって読み上げられたときに通知されます。


これらの機能を組み合わせて使用すると、メッセージの受信と開封による信頼性が向上します。 これらの機能を使用する新しいケアチームは、患者ごとに作成することができます。 これらの機能はポリシーベースであり、個人またはチーム全体に割り当てることができます。

詳細については、「[医療機関向けのセキュリティで保護されたメッセージングポリシーの概要](messaging-policies-hc.md)」を参照してください。

また、セキュリティで保護されたメッセージングに関連して、医療機関が他のテナントをフェデレーションし、豊富なテナント間通信を実現することができます。 (「 [Microsoft Teams で外部アクセス (フェデレーション) を管理](../../manage-external-access.md)する」を参照してください)。

## <a name="firstline-worker-integration"></a>Firstline Worker の統合

Microsoft Teams は Firstline Worker と統合されています。これは、シフトのスタッフ機能の調整に使用できます。

 次の記事を参照してください。

- [Microsoft Teams で Microsoft StaffHub teams をシフトに移行する](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [Microsoft Teams で組織のシフト アプリを管理する](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
