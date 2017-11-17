---
title: "Microsoft Teams のセキュリティとコンプライアンスの概要 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "監査および報告、コンプライアンスのコンテンツ検索、電子情報開示などを含む、Microsoft Teams のセキュリティとコンプライアンス機能の概要"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 83cad5896079173300d5aeaa40835f7ffa4d5074
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Microsoft Teams のセキュリティとコンプライアンスの概要
======================================================

Microsoft Teams は、お客様の期待に応える高度セキュリティおよびコンプライアンス能力を備えた Office 365 ハイパースケールのエンタープライズクラスのクラウド上に構築されています。

Teams は販売開始時点から Tier C 準拠です。これにより、ISO 27001、ISO 27018、SSAE16 SOC 1 および SOC 2、HIPAA、EU モデル契約条項 (EUMC) といった標準に対応します。Microsoft コンプライアンス フレームワークにおいて、Microsoft は Office 365 のアプリケーションとサービスを 4 つのカテゴリに分類しています。各カテゴリは、そのカテゴリのリストに記載されるために Office 365 サービスや関連するマイクロソフトのサービスが満たす必要のある、特定のコンプライアンス コミットメントによって定義されます。

業界をリードするコンプライアンスへの取り組みを実施しているコンプライアンス カテゴリ C および D のサービスは、既定で有効になっています。カテゴリ A と B のサービスでは、組織全体に対してオンまたはオフにする制御が用意されています。詳細については、「[Compliance Framework for Industry Standards and Regulations (業界の規格と規制のコンプライアンス フレームワーク)](https://go.microsoft.com/fwlink/?linkid=855777)」をご覧ください。Microsoft Teams はクラウド セキュリティ アライアンス (CSA) にも準拠しています。

Teams はチーム全体および組織全体の 2 要素認証、Active Directory を介したシングル サインオン、移動中および静止中のデータの暗号化も実施します。ファイルは SharePoint に格納され、SharePoint 暗号化が適用されます。メモは OneNote に格納され、OneNote 暗号化が適用されます。

監査ログ検索、電子情報開示、訴訟ホールド (チャネル、チャット、ファイルを対象とした)、Microsoft Intune 内でのモバイル アプリ管理のサポートを追加しました。

これらのツールは Office 365 のセキュリティとコンプライアンスのポータルにあり、次の機能を提供しています。

-   監査と報告

    -   監査ログ検索は、Office 365 のセキュリティ/コンプライアンス センターに直結しています。監査イベントに関するアラートと報告の設定、管理や調査の目的で使用するワークロード固有または汎用のイベント セットのエクスポート、無制限の監査タイムラインといった機能を提供します。すべての監査ログデータ、更なる分析を目的としたフィルタリングやエクスポートを利用して、Office 365 セキュリティ/コンプライアンス センター内でアラートを設定できます。

-   コンプライアンスのコンテンツ検索

    -   コンテンツ検索では、豊富なフィルタリング機能を使用して Microsoft Teams を検索でき、検索結果をコンプライアンスや訴訟のサポート用の特定のコンテナにエクスポートできます。この操作は電子情報開示ケースの有無に関わらず実行できます。

-   電子情報開示

    -   電子情報開示とは、訴訟または調査における開示要求に対応するための電子保持情報 (ESI) の電子的な特定、収集、生成です。

    -   この機能には、Teams データのケース管理、保持、検索、分析、エクスポートが含まれます。チャット、メッセージング、ファイル データが対象になります。

    -   お客様はインプレース電子情報開示または [Advanced eDiscovery](https://support.office.com/en-us/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4) を利用できます。

    -   次の表にその違いを示します。


| |インプレース電子情報開示  |Advanced eDiscovery  |
|---------|---------|---------|
|ケース管理     |X        |X         |
|アクセス制御  |X         |X         |
|コンテンツ検索     |X         | X        |
|保持   |X         | X        |
|エクスポート     |X         |X         |
|重複検出     |-         |X         |
|機会学習を使用した関連性検索    |-         |X         |
|非構造化データ分析      |-         |X         |


-   訴訟ホールド

    -   Microsoft Teams のチームにインプレース保持または訴訟ホールドが適用されると、そのホールドはグループ メールボックスに実施されます。

    -   訴訟ホールドの場合は、通常、電子情報開示ケース内に適用されます。

次の図は、Exchange と SharePoint の両方へのチーム データのワークフローを示しています。

![Exchange と SharePoint への Teams データのワークフローの図。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> チームのコンテンツの開示には最大で 24 時間の遅延が発生する場合があります。

さらに、Microsoft は次のセキュリティ機能を Teams に追加する予定です。 これらの機能が利用可能になる際には、お客様がこれらの機能をどのように利用できるかを説明するガイダンスを提供する予定です。

-   テナント固有の保持ポリシー

-   情報漏洩対策 (DLP)

-   カスタマー ロックボックス

-   権利管理


| | | |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |組織で必要とされているセキュリティとコンプライアンスの機能を教えてください。組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |次のステップ         |次の表に示す必須のセキュリティとコンプライアンスの機能を文書化します。         |

<a name="licensing"></a>ライセンス
---------------

情報保護機能については、Office 365 サブスクリプションとそれに関連付けられたスタンドアロン ライセンスによって利用可能な機能セットが決定します。

|情報保護機能   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|アーカイブ|-  |-   |-   |はい   |はい   |
|インプレース電子情報開示|-   |-   |-   |はい   |はい   |
|Advanced eDiscovery|-   |-   |-   |-   |はい   |
|訴訟ホールド|-   |-   |-   |はい   |はい   |
|コンプライアンスのコンテンツ検索|- |- |- |はい |はい |
|監査と報告|はい |はい |はい |はい |はい |
|条件付きアクセス* |はい |はい |はい |はい |はい |
\*条件付きアクセスには追加のライセンスが必要


| |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |判断ポイント         |お客様の組織はセキュリティとコンプライアンスのビジネス要件を満たすために必要なライセンスを所有していますか?         |
|![次のステップ アイコン。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |次のステップ         |お客様の組織の現在のライセンスを調べて、コンプライアンスとセキュリティのすべてのビジネス要件を満たしていることを確認します。         |

上記の機能を有効にする前に、Office 365 管理センターのセキュリティ/コンプライアンス センターにアクセスしてください。 既定では、テナントの管理者がアクセス権を持ちます。

コンテンツ検索と電子情報開示については、セキュリティ/コンプライアンス センター内で有効にする操作は不要です。

<a name="location-of-data-in-microsoft-teams"></a>Microsoft Teams のデータの場所
-----------------------------------

Teams 内のデータはテナント アフィニティに基づく地域に存在します。 現在、Teams は南北アメリカ、EMEA、および APAC 地域をサポートしています。 

2017 年 11 月 1 日時点では、英国においては新しいテナントに対してのみ Teams によるデータ常駐が提供されます。 新しいテナントは、Microsoft Teams に 1 人のユーザーもサインインさせていない任意のテナントとして定義されます。

> [!NOTE]
> 英国内の既存のテナントは、(2018 年に予定されている) 移行プランが公開されるまで EMEA に残り続けます。

詳細については、Microsoft Teams 技術コミュニティの英国のデータ常駐の立ち上げに関する[ブログ投稿](https://go.microsoft.com/fwlink/p/?linkid=862275)をご覧ください。

<a name="privacy-in-microsoft-teams"></a>Microsoft Teams でのプライバシー
--------------------------

Office 365 のユーザーとして、お客様はデータを所有して管理します。Microsoft が、お客様が購読しているサービスの提供以外の目的でお客様のデータを使用することはありません。Microsoft は、サービス プロバイダーとして、広告や他のサービスと無関係な目的のためにお客様のメール、ドキュメント、チームを調べることはありません。Microsoft はアップロード済みのコンテンツに対してアクセス権を持ちません。OneDrive for Business や SharePoint Online と同様に、お客様のデータはテナント内にあります。

信頼およびセキュリティに関連する情報について詳しくは、[*Office 365 セキュリティ センター*](https://go.microsoft.com/fwlink/?linkid=855779)にアクセスしてください。 Teams は Office 365 セキュリティ センターと同じガイダンスと原則に従っています。
