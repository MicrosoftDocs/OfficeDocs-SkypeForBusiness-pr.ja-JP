---
title: クラスチームを作成するための推奨方法とベストプラクティス
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: 学校のクラスチームの推奨する作成方法とベストプラクティスについて説明します。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e85ef79247bdf35c3c116504af23728a0d268ca5
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429329"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>クラスチームを作成するための推奨方法とベストプラクティス

Microsoft Teams for Education は、教育機関向けに  [特別なチームタイプ](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) を提供しています。 [クラスチームタイプ](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)は教室での使用を目的として設計されており、教室のニーズを次の特定の機能でサポートします。  

- 宿題
- 成績
- OneNote クラスルームノートブック  
- 学生向けの読み取り専用コンテンツを保護するための[授業で使用する教材用フォルダー](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) 
- 生徒が追加される前に教師がクラスを設定できるようにするための[教師の早期アクセス](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) 
- 授業妨害をする学生をミュートする機能やその他の特別な権限  

クラスチームを作成する方法はいくつかあります。Teams for Education には、作業を簡易化する独自の導入ツールセットがあります。 ニーズに合わせて、最適に且つ適切に導入できるように、さまざまなオプションについて説明していきます。  

## <a name="automatic-team-creation-using-sds"></a>SDS を使用したチームの自動作成

**この機能は 2020 年 7 月末ごろ、登場いたします。**

チーム作成を自動化することで、IT 管理者と教師の作業時間を短縮します。 この機能によって、教師はすべてのクラスチームを作成し、サインイン時にセットアップできるようになります。 [School Data Sync（SDS）](https://docs.microsoft.com/SchoolDataSync)は、Office 365 Education の無料ツールで、教育機関の記録システム（学生情報システム（SIS）や学習管理システム（LMS）など）からデータを読み取ります。 SDS はデータを使用して、Office 365 のセットアップをさまざまな方法で強化します。例えば、クラスチームを一括で作成したり、情報システムと常に同期して、講師や学生のメンバーシップをクラス登録の変更に応じて更新します。 SDS は、任意の記録システムからデータをインポートでき、世界中の[SIS ベンダー](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support)への組み込みコネクタを備えています。 推奨する SDS の利点。  

### <a name="benefits"></a>利点

- クラスチームの自動作成とメンテナンス – 教師は Teams にサインインした直後から授業を始めることができます。
- メンバーシップは SIS/LMS と同期して、学生のメンバーシップの変更を維持します。
- 無料の導入アシスタンスを提供する EDU カスタマーサクセスチーム。
- [教師の早期アクセス](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): 教育者は、学生を受け入れる前にチームを準備しなければなりません。  
- オプションでユーザーを作成し、Office 365 ライセンスを適用します。
- Teams ポリシーを含む Office 365 全体で使用するセキュリティグループを作成します。
- 管理委任と[教師パスワードのリセット](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)のための管理ユニットを作成します。 
- 組み込みのエラーと再試行の処理、バックオフの抑制、大規模な処理のためのセッションの安定性により、管理者の作業が軽減されます。  
- 不要になったグループとチームの名前を変更してアーカイブする組み込みのクリーンアップ機能。
- [Grade Sync](https://docs.microsoft.com/schooldatasync/grade-sync): 教師はすべての採点を Teams で行い、Teams の成績を SIS 成績表に自動的に書き戻すことができます。 
- [学生データ保護](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): 生徒が Microsoft 以外のアプリを使用するのを防ぎ、保護者の同意を追跡および管理します。 
- インポートされたデータは、ユーザーの役割、組織（学校）、その他の重要なデータを用いて、Education Insights を強化するために使用されます。  

### <a name="considerations"></a>考慮事項

SDS は2つのステップでチームを作成します。 最初のステップでは、Azure Active Directory （Azure AD）に Microsoft 365 グループを作成し、2 番目のステップでは、そのグループを自動的にチームに変換します。 チームを作成する2番目のステップは、SDS ではオプションです。 管理者は、導入時間と結果として生じる可能性のある未使用のチームの数によっては、チームを自動作成したがらない可能性があります。 500,000 以上のチームを持つ機関には、SDS でチームの自動作成トグルをオフにし、[教師主導のチーム作成方法](#educator-led-team-creation-from-office-365-class-groups)を使用するようお勧めします。  

### <a name="get-started"></a>はじめに

まず、[School Data Sync（SDS）](https://docs.microsoft.com/SchoolDataSync)にアクセスし、[https://aka.ms/sdssupport](https://aka.ms/sdssupport)導入アシスタンスにご連絡ください。  

## <a name="educator-led-team-creation-from-office-365-class-groups"></a>Office 365 クラスグループからの教師主導のチーム作成

**この機能は、2020年8月中旬までに、登場します。**

教師主導のチーム作成は、教師が必要なクラスをすばやく簡単に作成したい場合、導入オプションとして優れています。 500,000以上のチームを持つ機関には、無関係に作成されるチームの数を最小限に抑えることができるためこの方法をお勧めします。  

このハイブリッドアプローチでは、SDS を使用して各クラスのグループを作成するか（推奨）、または[Graph API ](https://docs.microsoft.com/graph/api/educationroot-post-classes)を使用して独自にグループを作成できます。 クラスグループの準備ができましたら、教育者は、[**推奨クラス**]アイコンを使用してグループをチームに変換できます。

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="推奨クラスアイコンを示すスクリーンショット":::

### <a name="benefits"></a>利点

- [教師の早期アクセス](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): 教育者は、学生を受け入れる前にチームを準備しなければなりません。  
- 未使用の不要なチームの数を減らします。 クラスを準備したり提案できますが、教師がそれらのクラスを使用するつもりがない場合は作成されることはありません。 500,000以上のチームを持つ大規模な機関には、混乱を避けるため、このオプションをお勧めします。
- SDS
    - メンバーシップは SIS/LMS と同期して、学生のメンバーシップの変更を維持します。
    - 無料の導入アシスタンスを提供する EDU カスタマーサクセスチーム。
    - オプションでユーザーを作成し、Office 365 ライセンスを適用します。
    - Teams ポリシーを含む Office 365 全体で使用するセキュリティグループを作成します。
    - 管理委任と[教師パスワードのリセット](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset)のための管理ユニットを作成します。
    - 組み込みのエラーと再試行の処理、バックオフの抑制、大規模な処理のためのセッションの安定性により、管理者の作業が軽減されます。 
    - 不要になったグループとチームの名前を変更してアーカイブする組み込みのクリーンアップ機能。 
    - [Grade Sync](https://docs.microsoft.com/schooldatasync/grade-sync): 教師はすべての採点を Teams で行い、Teams の成績を SIS 成績表に自動的に書き戻すことができます。 
    - [学生データ保護](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): 生徒が Microsoft 以外のアプリを使用するのを防ぎ、保護者の同意を追跡および管理します。 
    - インポートされたデータは、ユーザーの役割、組織（学校）、その他の重要なデータを用いて、Education Insights を強化するために使用されます。
- Graph API
    - 追加の柔軟性と管理。
    - SDS と統合する必要ありません。

### <a name="considerations"></a>考慮事項

- 完全に自動化されておらず、教師のアクションを必要とします。
- チームを作成する権限がない教師でも、[こちら](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)に示すように、既存のグループからチームを作成することができます。
- Graph API は、スクリプトの作成や実行、クラスグループの作成時に発生した問題の修正など高度な技術的専門知識と時間を必要とします。

### <a name="get-started"></a>はじめに

SDS メソッドではまず、[学校データ同期（SDS）](https://docs.microsoft.com/SchoolDataSync)に移動し、[https://aka.ms/sdssupport](https://aka.ms/sdssupport)導入アシスタンスにご連絡ください。 

Graph API メソッドの利用方法は、「[Graph API](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http)」および「[クラスチームを作成する](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)」を参照してください。  

> [!NOTE]
> SDS でこの方法を使用するには、SDS プロファイルで自動チーム作成トグルをオフにしなければなりません。 2 つの SDS プロファイルを使用して、必須およびオプションのクラスチームに対して、自動作成と教師主導のチーム作成を組み合わせて使用することもできます。

## <a name="powershell-script-using-graph-apis"></a>Graph API を使用した PowerShell スクリプト

PowerShell では、チームやチャネルを作成するためにスクリプトを書いたり、、設定を自動的に構成することができます。 管理者は、まずグループを作成し、教師と生徒を追加してから、[こちら](https://docs.microsoft.com/graph/teams-create-group-and-team)で説明されているようにチームを作成しなければなりません。 Microsoft Graph API では、チームを作成、構成、複製、アーカイブすることもできます。 詳細については、「[Microsoft Graph APIを使用してMicrosoft Teamsで作業する](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview)」、「[ Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams)」および「[クラスチームを作成する](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type)」を参照してください。 グラフAPI は管理と柔軟性を高めますが、高度な技術的専門知識が必要であり、初期設定に時間がかかります。  

### <a name="benefits"></a>利点

- 追加の柔軟性と管理。
- 教師への早期アクセスチームを作成するか、生徒へのチームへの即時アクセスを作成するオプション。  
- [グループからチームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group)すると、教師は早期アクセスが可能になり、Azure AD グループの学生メンバーシップの変更が同期されます。

### <a name="considerations"></a>考慮事項

- スクリプトの作成や実行、クラスグループの作成時に発生した問題の修正など高度な技術的専門知識と時間を必要とします。
- 組み込みのエラー処理や再試行ロジックはありません。
- メンバーシップの変更は SIS と同期されません。 

> [!NOTE]
> クラスチームには非表示のグループメンバーシップが必要ですので、クラス内の教師と生徒だけがそのクラスのメンバーを見ることができます。 Office 365 クラスグループを作成するには、「[クラスチームを作成する](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http)」を参照して、同じプライバシー要件を満たします。

## <a name="manual-team-creation"></a>チームの手動作成

生徒と教師に Teams を最大限に活用してもらうには、使用に際してのハードルが低く、各自のニーズに合うようにカスタマイズできる柔軟性があることが大切です。 ユーザーは、チーム作成機能を使用してチームエクスペリエンスを調整できます。 教育者は独自のクラスタイプのチームを設定し、[こちら](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)に示すように生徒を招待します。 教育者は、[チームに生徒を追加する](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)、[参加コードを共有する](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)、または[チームへのリンクを共有する](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)ことにより、生徒を招待できます。 可能であれば、教育者がチームに生徒を追加し、生徒がアクセスできるようにし整え、チームに生徒を追加したことを通知することをお勧めします。

### <a name="benefits"></a>利点

- 教師のための追加の柔軟性。
- チームの即時作成とアクセス。  

### <a name="considerations"></a>考慮事項

- 教師によるアクションおよび時間を必要とします。
- 学生のメンバーシップは SIS と同期されず、手動で管理しなければなりません。
- 教師がチームに早期アクセスすることはできません。 学生はすぐにアクセスできます。

## <a name="recommended-best-practices"></a>推奨されるベストプラクティス

- 早期導入！ 早期に導入して、すべてが確実に機能し、初日の準備ができるようにします。 SDS を使用する場合、SDS の導入には完全な学生メンバーシップは必要ありません。 学生メンバーシップ情報が SIS で利用可能になると、生徒が同期されます。
- チームが 500,000 以上ある場合、[教師主導のチーム作成方法](#educator-led-team-creation-from-office-365-class-groups)を使用することをお勧めします。 関連性があり必要なクラスチームのみを作成することで、未使用のチームと混乱を減らします。  
- SDSの自動チーム作成に問題があり（クラスが不足するなど）、教師がチームをすぐに必要とする場合は、[教師主導のチーム作成方法](#educator-led-team-creation-from-office-365-class-groups)を使用して再試行できます。 [チームの手動作成](#manual-team-creation)は別のソリューションですが、チームメンバーシップを更新し続けることはできません。  
- テナントチームの上限は500,000チームです。 したがって、管理者は未使用のチームの数を積極的に減らして、制限に達したり、セットアップ時間を延長する必要がないようにしないようにしなければなりません。 制限の詳細については、「[Microsoft Teams の制限事項と仕様](limits-specifications-teams.md)」を参照してください。  
