---
title: Microsoft Teams で承認アプリを管理する
author: LanaChin
ms.author: v-lanachin
ms.reviewer: farhazk
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Microsoft Teams で組織の承認アプリを管理する方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 866025dad342f5abfb5b0722391dc754b3f00dd5
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68655843"
---
# <a name="manage-the-approvals-app-in-microsoft-teams"></a>Microsoft Teams で承認アプリを管理する

Microsoft Teams ユーザーは、個人用アプリとして承認アプリを利用することができます。
承認アプリは、Teams 内の構造化された承認と構造化されていない承認の両方に対して、監査、コンプライアンス、説明責任、およびワークフローを簡単にする方法を提供します。 

 ![承認アプリを表示する。](media/approvals-selection.png)

ユーザーは承認アプリをピン留めしてメニュー バーに保存できます。

 ![PIN オプションを使用する承認アプリを表示する。](media/approvalApp-pin.png)

承認アプリから最初の承認が作成されると、既定の Microsoft Dataverse 環境にて承認ソリューションがプロビジョニングされます。 承認アプリから作成された承認は、既定の Microsoft Dataverse 環境に保存されます。

この記事では、承認アプリの要件と役割について説明します。

> [!NOTE]
> この機能は、政府機関コミュニティ クラウド High (GCCH)、米国国防総省 (DOD) のユーザーにはリリースされていません。

## <a name="required-permissions-and-licenses"></a>必要なアクセス許可とライセンス

承認アプリを展開するには、次のアイテムに対する権限が必要です。

- Microsoft Dataverse データベースを作成する権限。

- [powerautomate.microsoft.com](https://powerautomate.microsoft.com/) のアカウント

- ターゲット環境における管理者の役割。

- [Power Automate](/power-automate/get-started-approvals)、Office 365、または Dynamics 365 のライセンス。

- ユーザーが新しい承認テンプレートを設定するには、Microsoft Forms のライセンスが必要です。

承認アプリを使用するには、Power Automate のライセンスが必要です。最初の承認割り当てで、ターゲット環境に [承認ユーザー] ロールにアカウントが自動的に追加されます。

## <a name="storage-with-microsoft-dataverse"></a>Microsoft Dataverse を使用したストレージ

共通データ モデル (CDM) は、Microsoft Dataverse のビジネス アプリケーションや分析アプリケーションで使用される共有データ言語です。 これは、Microsoft とそのパートナーによって公開された、一連の標準化された拡張可能なデータ スキーマで構成されており、アプリケーションとビジネス プロセス全体でデータとその意味の一貫性を実現します。 [Microsoft Power Platform の共通データ モデル](/power-automate/get-started-approvals)の詳細については、以下をご覧ください。

[承認ワークフロー](/power-automate/modern-approvals)の詳細。

テンプレートから作成された承認は、タイトル、詳細、テンプレート ID などのデータを引き続き Microsoft Dataverse に保存します。 承認要求で送信される応答は Forms に保存されます。 [Microsoft Forms のデータの保存場所](https://support.microsoft.com/office/data-storage-for-microsoft-forms-97a34e2e-98e1-4dc2-b6b4-7a8444cb1dc3#:~:text=Where%20data%20is%20stored%20for%20Microsoft%20Forms.%20Microsoft,European-based%20tenants%20is%20stored%20on%20servers%20in%20Europe)の詳細。

>[!Note]
>Microsoft Forms サイトで Forms テンプレートを削除すると、承認テンプレートが破損し、ユーザーは要求を開始できなくなります。 ユーザーが Microsoft Forms で削除された承認テンプレートを開こうとすると、"CDB TableNotFound" というエラーが表示されます。

組織を対象とするテンプレートはテナントの有効期間が、チームを対象とするテンプレートはチームの有効期間が同じです。 そのため、チームを完全に削除すると、関連するテンプレートも削除されます。

## <a name="approvals-teams-app-permissions"></a>Teams アプリの権限の承認

Teams アプリの承認では、次の機能にアクセスできます。

- メッセージやデータを受信します。

- メッセージと通知を送信します。

- Teams が提供するヘッダーを必要とすることなく、個人用アプリとダイアログをレンダリングします。

- [名前]、[電子メールアドレス]、[会社名]、[優先する言語] などの個人用プロフィール情報にアクセスします。

- チーム メンバーがチャネルで提供するメッセージとデータを受信します。

- チャネルでメッセージと通知を送信する。

- チームの情報にアクセスする:
  - チーム名
  - チャネル リスト
  - 名簿 (チーム メンバーの名前とメール アドレス)。

- チームの情報を使用してメンバーに連絡します。

承認テンプレートのアクセス許可

- すべてのチーム所有者は、所有するチームの承認テンプレートを作成できます。

- 管理者が組織全体のテンプレートを初めて作成すると、グローバル管理者と Teams のサービス管理者を含め、テナント内のすべての管理者に対して Azure Active Directory (AAD) グループが自動的に作成されます。 これらの管理者は、グループの所有者として追加され、組織テンプレートを共同管理できるようになります。 チームが作成された後に組織に新しく加わった管理者が組織全体のテンプレートを管理するための同じアクセス許可を取得するには、手動でグループ所有者として追加される必要があります。

> [!Note]
> 管理者がグループを削除すると、関連するすべてのデータを復元するために Azure Active Directory (AAD) ポータルでチームを復元できる期間が 1 か月間あります。 1 か月を過ぎると、または管理者がごみ箱内でこのグループを削除すると、関連するすべてのデータが失われます。

## <a name="disable-the-approvals-app"></a>承認アプリを無効にする

承認アプリは既定で利用可能です。 Teams 管理センターでアプリを無効にできます。

  1. Teams 管理センターにサインインします。

  2. **[Teams アプリ]** > **[アプリの管理]** の順に移動します。

  3. 承認アプリを検索します。

     ![強調表示されている [Teams アプリ] > [アプリの管理] を使用して、管理センター ナビゲーションを表示する。](media/manage-approval-apps.png)

  4. **[承認]** を選択します。

  5. 切り替えを選択して、組織のアプリを無効にします。

     :::image type="content" alt-text="承認アプリの詳細を表示する。" source="media/approvals-details-new.png" lightbox="media/approvals-details-new.png":::

## <a name="pin-approvals-to-teams"></a>Teams に承認をピン留めする

### <a name="use-the-tailored-frontline-app-experience-to-pin-approvals-and-other-apps-to-teams"></a>カスタマイズされたフロントライン アプリ エクスペリエンスを使用して、承認やその他のアプリを Teams にピン留めする

Teams のカスタマイズされたフロントライン アプリ エクスペリエンスは、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)を持つユーザーにとって Teams で最も関連性の高いアプリをピン留めします。 ピン留めされたアプリには、[承認]、Walkie Talkie、[タスク]、および [シフト] が含まれます。 既定では、この機能はオンになっており、現場の従業員はニーズに合わせてすぐに使えるエクスペリエンスを提供します。

このアプリは、アプリ バー (Teams デスクトップ クライアントの横、および Teams モバイル クライアントの一番下にある) にピン留めされ、ユーザーはそこからすばやく簡単にアプリにアクセスできます。

その他設定したアプリ ポリシーでのエクスペリエンスの動作など、詳細については、「[現場の従業員向けの Teams アプリの調整](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)」を参照してください。

### <a name="use-an-app-setup-policy-to-pin-approvals-to-teams"></a>アプリのセットアップ ポリシーを使用して、Tasks をチームにピン留めする

アプリのセットアップ ポリシーを使用すると、チームをカスタマイズして、ユーザーにとって最も重要なアプリをユーザーに固定できます。

ユーザーの承認アプリをピン留めするには、グローバル (組織全体の既定) ポリシーを編集するか、アプリセットアップ ポリシーでカスタム ポリシーを作成して割り当てます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を参照してください。

## <a name="retention-policy"></a>アイテム保持ポリシー

[承認] アプリから作成された承認は既定の Microsoft Dataverse 環境に保存されます。現時点では、バックアップはサポートされません。 詳細については、「[環境のバックアップと復元の方法Power Platform \|Microsoft Docs](/power-platform/admin/backup-restore-environments)」をご覧ください。

Forms に保存されているデータは、チーム所有者が Microsoft Forms Web アプリの **[削除されたフォーム]** タブからクリーンアップするまで削除されません。

## <a name="conditional-access-policies"></a>条件付きアクセス ポリシー

現時点では、Teams の承認アプリでは、Microsoft Teams 用に設定されている条件付きアクセス ポリシーはサポートされていません。

## <a name="data-limitations"></a>データの制限事項

Microsoft Forms の現在の機能に基づいて、各チームには最大 400 個の承認テンプレートを含めることができ、各テンプレートは 最大 50,000 件の要求を収集できます。

## <a name="auditing"></a>監査

The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center. You can view the audit log.

1. Microsoft 365 コンプライアンス センターにアクセスします。

2. [**監査**］ セクションを選択 します。

3. 「**Microsoft Teams の承認アクティビティ**」からアクティビティを検索します。

次のアクティビティを検索できます。

- 新しい承認要求を作成する

- 承認要求の詳細を表示する

- 承認要求が承認されました

- 承認要求が拒否されました

- 承認要求がキャンセルされました

- 共有された承認要求

- 承認要求に添付されているファイル

- 再割り当てされた承認要求

- 電子署名が追加された承認要求

- 電子署名要求を表示する

- 電子署名要求を確認する

- 電子署名要求がキャンセルされました

- 新しいテンプレートを作成する

- 既存のテンプレートを編集する

- テンプレートの有効化/無効化

- テンプレートを表示する

Power Automate 内の他の監査承認にアクセスするには、プライマリ承認エンティティの承認、承認要求、承認応答の既定の環境において、監査を有効にして構成します。 作成、更新、および削除の操作は、承認レコードにて監査可能なイベントです。 詳細については、「[セキュリティとコンプライアンスのための監査データとユーザー アクティビティ - Power Platform \|Microsoft Docs](/power-platform/admin/audit-data-user-activity)」をご覧ください。

監査は、「[Microsoft 365 セキュリティとコンプライアンス センター](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)」にてさらにカスタマイズできます。

1. 構成済みのレポートを使用するには、「Microsoft 365 のセキュリティとコンプライアンス」にサインインします。

2. 「**検索と調査**」を選択します。

3. 監査ログを検索し、[**Dynamics 365 アクティビティ**］を選択 します。

詳細については、「[Microsoft Dataverse モデルベース アプリ アクティビティ ログ - Power Platform](/power-platform/admin/enable-use-comprehensive-auditing)」を参照してください。

## <a name="security"></a>セキュリティ

ユーザーは、Teams 承認アプリから新しい承認を作成することができ、自分が送受信した承認を表示することができます。 ユーザーは、要求の回答者または閲覧者ではない限り、他のユーザーが作成した承認にはアクセスできません。

> [!Note]
> ユーザーが、承認の作成されたチャットまたはチャネルの一部である場合、要求の閲覧者の役割が与えられます。 承認が作成された際に、その役割が与えられなかった場合は、要求に対してアクションを実行することはできません。

## <a name="approvals-e-signature-integration"></a>承認における電子署名の統合

承認アプリの電子署名機能を使用するには、使用する特定の電子署名プロバイダーのライセンスが必要です。 組織用にライセンスを取得するには、プロバイダーのサイトにアクセスする必要があります。

### <a name="enable-or-disable-e-signature-providers"></a>電子署名プロバイダーを有効または無効にする

Teams 管理センターを使用して、承認アプリでユーザーが利用できるサード パーティの電子署名プロバイダーを制御できます。 既定では、電子署名プロバイダーは承認アプリで有効になっています。 電子署名プロバイダーを無効にすると、ユーザーは承認を作成するときにそのプロバイダーにアクセスできなくなります。 また、ユーザーは、そのプロバイダーを使用して作成された電子署名要求を表示することもできません。

1. Teams 管理センターの左側のナビゲーションで、**[Teams アプリ]** > **[アプリを管理]** の順に移動します。
2. 承認アプリを検索し、それを選択します。
3. **[設定]** タブに移動し、次のいずれかの操作を行います。

    - Adobe Sign を有効または無効にするには、トグルを **[On]** または **[Off]** に切り替えます。
    - DocuSign を有効または無効にするには、トグルを **[On]** または **[Off]** に切り替えます。
4. **[送信]** を選択します。

承認アプリから作成された電子署名の承認は、選択したプロバイダーのクラウド環境に保存されています。 電子署名に関するデータをエクスポートするには、プロバイダーのサイトに移動する必要があります。 電子署名契約の保存、エクスポート、および保持の詳細については、プロバイダーのドキュメントを参照してください。
