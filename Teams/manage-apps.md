---
title: Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Teams アプリを管理する方法について説明します。 アプリの許可またはブロック、組織レベルの状態とアプリのプロパティの確認、カスタム アプリのアップロード、アプリ設定の管理について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 25e540a7709ab12b73a97cc94b1350630c302197
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529729"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターで Teams アプリを管理する

Teams 管理センター ポータルの **[Teams アプリ** ] ページで、組織のアプリを管理します。 [アプリの管理] ページを使用して、組織のアプリ カタログにあるすべての Teams アプリを表示および管理できます。

![[アプリの管理] ページのスクリーンショット。](media/manage-apps.png)

Teams 管理センターを使用するには、グローバル 管理または Teams 管理者ロールが必要です。 詳細については、次のヘルプ記事を参照してください。

* [Teams 管理者ロール](./using-admin-roles.md)。
* [Microsoft 365 管理者ロール](/microsoft-365/admin/add-users/about-admin-roles)

アプリを管理するには、ポリシーを使用して、ユーザーのアクセス許可、アプリのインストール、組織内に作成されたカスタム アプリのアップロードを制御します。 ポリシーについては、「 [アプリ ポリシーの概要](app-policies.md)」を参照してください。

> [!NOTE]
> [アプリの管理] ページは、Microsoft 365 Government Community Cloud High (GCCH) または国防総省 (DoD) の Teams の展開では使用できません。

アプリの作成中に、開発者はアプリ ID を作成してマニフェスト ファイルに追加します。 この外部アプリ ID は、列設定から列 `External app ID` を有効にした後、[アプリの管理] ページで表示できます。 カスタム アプリのアプリの詳細ページでも表示できます。 この ID は、カスタム アプリにのみ適用されます。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>アプリ管理のユース ケースと使用可能なインターフェイス

ほとんどのアプリ管理ユース ケースを実現するためのオプションは、Teams 管理センターで使用できます。 さらに、一部のオプションは他のポータルで使用できます。

| アプリ管理のユース ケース | インターフェイスへのリンク | ドキュメント |
|:----|:----|:----|
| **Teams 管理センターで** | | |
| アプリを許可およびブロックすることで、組織内のユーザーが使用できるアプリを制御します。 カスタム アプリをアップロードして承認することもできます。 このページでアプリを管理した後、アプリのアクセス許可とアプリのセットアップ ポリシーを使用して、組織のアプリ ストア内の特定のユーザーが利用できるアプリを構成できます。 | [Teams 管理センターでアプリを管理する](https://admin.teams.microsoft.com/policies/manage-apps) | 現在の記事 |
| アプリのアクセス許可ポリシーは、組織内の Teams ユーザーが使用できるようにするアプリを制御します。 グローバル (組織全体) の既定のポリシーを使用してカスタマイズすることも、組織のニーズに合わせて 1 つ以上のポリシーを作成することもできます。 | [アクセス許可ポリシー](https://admin.teams.microsoft.com/policies/app-permission) | [アプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md) |
| アプリセットアップ ポリシーは、Teams アプリを使用してユーザーがアプリを使用できるようにする方法を制御します。 グローバル (組織全体の既定) ポリシーを使用し、それをカスタマイズするか、カスタム ポリシーを作成して一連のユーザーに割り当てます。 | [セットアップ ポリシー](https://admin.teams.microsoft.com/policies/app-setup) | [アプリのセットアップ ポリシーを管理する](teams-app-setup-policies.md) |
| カスタム アプリをアプリ パッケージとして開発してアップロードし、組織のアプリ ストアで利用できるようにします。 | [アプリの管理] の組織全体の[アプリ](https://admin.teams.microsoft.com/policies/manage-apps)設定 | [カスタム アプリ ポリシーを管理する](teams-custom-app-policies-and-settings.md) |
| 組織のロゴ、カスタム背景、または色を使用して Teams アプリ ストアをカスタマイズできます。 | [ストアをカスタマイズする](https://admin.teams.microsoft.com/policies/customize-appstore) | [組織のアプリ ストアをカスタマイズする](customize-your-app-store.md) |
| Teams アプリの使用状況レポートには、使用中のアプリ、アクティブなユーザー、その他のアプリの使用状況に関する情報が表示されます。 | [使用状況レポート](https://admin.teams.microsoft.com/analytics/reports) | [Teams アプリの使用状況レポート](teams-analytics-and-reports/app-usage-report.md) |
| ユーザーは、ゲストとの会議やチャットをホストするときにアプリを追加できます。 また、外部でホストされている会議やチャットに参加するときに、ゲストが共有するアプリを使用することもできます。 ホスティング ユーザーの組織のデータ ポリシーと、そのユーザーの組織によって共有されているサードパーティアプリのデータ共有プラクティスが適用されます。 | [外部アクセス](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [ユーザーの種類に応じたアプリの動作](non-standard-users.md) |
| ゲスト アクセスを使用すると、企業データの制御を維持しながら、組織外のユーザーにアプリケーションやその他の Teams 機能へのアクセスを提供できます。 | [ゲスト アクセス](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams でのゲスト アクセス](guest-access.md) |
| 更新ポリシーは、Teams アプリにプレリリース機能またはプレビュー機能が表示される Teams および Office プレビュー ユーザーを管理するために使用されます。  | [Teams でポリシーを更新する](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams パブリック プレビュー](public-preview-doc-updates.md) |
| **Teams 管理センターの外部** | | |
| Microsoft 365 管理センターでサード パーティ製アプリのライセンスとサブスクリプションを管理する | [Microsoft 365 管理センター](https://admin.microsoft.com/#/licenses) | [サード パーティのアプリ サブスクリプションを管理する](/microsoft-365/commerce/manage-saas-apps) |
| Microsoft Purview コンプライアンス ポータルで Teams アプリ イベントを監査します。 | [監査](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams アクティビティ](audit-log-events.md#teams-activities) |
| アプリケーションには、組織とそのデータに対するアクセス許可を付与するには、管理者がすべてのユーザーのアプリケーションに同意する方法、ユーザーがアプリケーションに同意を付与する方法、またはアプリケーションを統合してセルフサービス アクセスを有効にしたり、ユーザーをアプリケーションに直接割り当てたりする管理者の 3 つの方法があります。 アプリの Graph アクセス許可を確認します。 ユーザーが提供したアクセス許可、または管理者が委任したアクセス許可を確認します。 | [Azure AD portal](https://aad.portal.azure.com/) | [アプリケーションに付与されたアクセス許可を確認する](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>カスタム アプリを組織のアプリ ストアに発行します。

[アプリの管理] ページを使用して、組織専用に構築されたアプリを発行します。 カスタム アプリを発行すると、組織のアプリ ストア内のユーザーがそれを使用できるようになります。 カスタム アプリを組織のアプリ ストアに発行するには 2 通りの方法があります。 いずれの方法を使うかは、アプリの取得方法によって決まります。

* [カスタム アプリの承認](#approve-a-custom-app): 開発者が Teams アプリ申請 API を使用してアプリを [アプリの管理] ページに直接送信する場合は、この方法を使用します。 その後、アプリの詳細ページから直接アプリを確認して発行 (または拒否) できます。
* [アプリ パッケージをアップロード](#upload-an-app-package): 開発者がアプリ パッケージを .zip 形式で送信する場合は、この方法を使用します。 アプリ パッケージをアップロードして、アプリを発行します。

### <a name="approve-a-custom-app"></a>カスタム アプリの承認

[アプリの管理] ページの **保留中の承認** ウィジェットは、開発者が Teams アプリ申請 API を使用してアプリを提出したときに通知を受け取ります。 新しく提出されたアプリには、"**送信済み**" の **公開状態** と、"**ブロックされた**" **状態** が表示されます。 アプリの詳細ページに移動してアプリの詳細を表示し、発行するには、**[発行の状態]** を **[発行]** に設定します。

また、開発者がカスタム アプリに更新プログラムを提出したときにも通知されます。 その後、アプリの詳細ページでアプリを確認して発行 (または拒否) できます。 すべてのアプリのアクセス許可ポリシーとアプリのセットアップ ポリシーは、更新されたアプリに適用されたままです。

賞については、「[Teams アプリ 申請 API を使用して送信されたカスタム アプリを発行する](submit-approve-custom-apps.md)」をご覧ください。

### <a name="upload-an-app-package"></a>アプリ パッケージのアップロード

開発者は、[Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio) を使用して Teams アプリ パッケージを作成し、.zip 形式で送信します。 アプリ パッケージがある場合は、それを組織のアプリ ストアにアップロードできます。

新しいカスタム アプリをアップロードするには、**[アップロード]** を選択してアプリ パッケージをアップロードします。 アップロード後、アプリは強調表示されないため、[アプリの管理] ページでアプリの一覧を検索して見つける必要があります。

アップロード後にアプリを更新するには、[アプリの管理] ページのアプリの一覧でアプリ名を選択し、**[更新]** を選択します。 更新を実行すると、既存のアプリが置き換わり、更新されたアプリに対してすべてのアプリアクセス許可ポリシーとアプリセットアップ ポリシーが引き続き適用されます。

詳細については、「[アプリ パッケージをアップロードしてカスタム アプリを発行する](upload-custom-apps.md)」を参照してください。

## <a name="allow-and-block-apps"></a>アプリの許可とブロック

[アプリの管理] ページは、組織レベルで個々のアプリを許可またはブロックする場所です。 利用可能なすべてのアプリと、現在の組織レベルのアプリの状態が表示されます。

アプリを許可またはブロックするには:

1. Teams 管理センター> Teams アプリ>アプリの管理に移動します。
1. アプリの一覧からアプリを選択します。
1. **[許可]** または [ブロック] を選択 **します**。

[アプリの管理] ページでアプリをブロックまたは許可すると、そのアプリは組織内のすべてのユーザーに対してブロックまたは許可されます。  Teams アプリのアクセス許可ポリシーでアプリをブロックまたは許可すると、そのポリシーが割り当てられているユーザーに対してブロックまたは許可されます。 ユーザーが任意のアプリをインストールして操作できるようにするには、[アプリの管理] ページからアプリを組織レベルで許可し、ユーザーに割り当てられているアプリのアクセス許可ポリシーを許可する必要があります。

 > [!NOTE]
 > アプリをアンインストールするには、アプリを右クリックし、**[アンインストール]** をクリックするか、左側の **[その他のアプリ]** メニューを使用します。

## <a name="manage-user-requests-to-unblock-apps"></a>アプリのブロックを解除するためのユーザー要求を管理する

ブロックされたアプリを使用できるように要求を表示できます。 要求は IT 管理者に送信され、Teams 管理センターでユーザー要求を表示および管理できます。

  :::image type="content" source="media/user-request.png" alt-text="ブロックされたアプリの承認を要求する":::

### <a name="view-a-request"></a>要求を表示する

 1. Teams 管理センターにサインインし、[アプリの[管理](https://admin.teams.microsoft.com/policies/manage-apps)] を選択します。

    :::image type="content" source="media/requested-apps1.png" alt-text="ユーザーによる要求" lightbox="media/requested-apps.png" border="true":::

 1. 各アプリの要求の数を表示して確認するには、[要求] の [ **ユーザー別の要求] 列で要求を** 並べ替えます。
 1. ブロックを解除するアプリの名前を選択すると、アプリの詳細ページが開きます。
 1. [ **要求の管理** ] を選択し、ポップアップ ダイアログに表示される手順を完了します。 アプリを承認する手順は、アプリをブロックするために使用される方法によって異なります。

    * アクセス許可ポリシーを使用してアプリがブロックされている場合は、 [アクセス許可](teams-app-permission-policies.md)ポリシーを変更してアプリを許可します。
    * すべてのユーザーに対してアプリがブロックされている場合は、 [アプリを許可します](#allow-and-block-apps)。
    * すべてのアプリがすべてのユーザーに対してブロックされている場合は、 [組織全体の設定を変更します](#manage-org-wide-app-settings)。

 管理者がアプリを許可している場合、要求が処理されたことをエンド ユーザーに通知しません。 ユーザーは、ストア内のアプリにアクセスして、アプリのブロックが解除されているかどうかを確認する必要があります。

### <a name="dismiss-a-user-request"></a>ユーザー要求を無視する

 1. ユーザー要求を無視するアプリの名前を選択します。
 1. [ **要求の管理** ] を選択し、ダイアログ ボックス **で [すべての要求を閉じる** ] を選択します。
 1. 要求が無視されると、ユーザー要求は 0 にリセットされます。

  :::image type="content" source="media/reject.png" alt-text="ブロックされたアプリの拒否。"border="true":::

管理者が要求を却下した場合、要求が処理されたことをエンド ユーザーに通知しません。 ユーザーは、ストア内のアプリにアクセスして、アプリのブロックが解除されているかどうかを確認する必要があります。

## <a name="apps-blocked-by-publishers"></a>発行元にブロックされているアプリ

ISV がグローバル アプリ ストアにアプリを発行する場合、アプリ エクスペリエンスを構成またはカスタマイズするために管理者が必要になる場合があります。 管理者は、アプリのセットアップ時にエンド ユーザーが利用できるようにします。

たとえば、Contoso Electronics は、Microsoft Teams 用のヘルプ デスク アプリを作成した ISV です。 Contoso Electronics は、その顧客がアプリを操作するときに期待どおりに機能するように、顧客がアプリの特定のプロパティを設定することを望んでいます。 管理者がアプリケーションを許可またはブロックする前に、Teams 管理センターで "**発行元 によってブロック済み**" として表示され、既定ではエンド ユーザーから非表示になっています。 アプリを設定するための発行元のガイダンスに従った後、状態を **[許可]** に変更してユーザーが利用できるようにしたり、状態を **[ブロック**] に変更してユーザーがアプリを使用できないようにしたりできます。

<!--- 
![Screenshot of blocked by publisher status in teams admin center.](media/blocked-by-publisher.png)
--->

## <a name="add-an-app-to-a-team"></a>チームにアプリを追加する

**[チームに追加]** ボタンを使用して、チームにアプリをインストールします。 このオプションは、チーム スコープにインストールできるアプリでのみ使用できます。 このオプションは、個人用スコープにのみインストールできるアプリでは使用できません。

1. その名前でアプリを検索し、アプリを選択します。 アプリの詳細ページを開かないでください。
1. **[チームに追加]** を選択します。

   :::image type="content" source="media/manage-apps-add-app-team-trimmed.png" alt-text="チーム スコープに追加できるアプリの [チームに追加] オプションのスクリーンショット。" lightbox="media/manage-apps-add-app-team.png":::

1. **[チームに追加]** ウィンドウで、アプリを追加するチームを検索し、チームを選択して、**[適用]** 選択します。

## <a name="customize-an-app"></a>アプリのカスタマイズ

組織のニーズに応じて、特定の外観を含めるアプリをカスタマイズできるようになりました。 「[Teams でアプリをカスタマイズする](customize-apps.md)」を参照してください。

## <a name="purchase-services-for-third-party-apps"></a>サードパーティ アプリのサービスを購入

[アプリの管理] ページから、組織内のユーザーに対してサード パーティ製アプリによって提供されるサービスのライセンスを直接検索して購入できます。 表の "**ライセンス**" 列は、アプリで有料 SaaS サブスクリプションを提供されているかどうかを示します。 **[今すぐ購入]** を選択して、プランと価格情報を表示し、ユーザーのライセンスを購入します。 詳細については、「[Microsoft Teams 管理センターで Teams サードパーティ製アプリのサービスを購入する](purchase-third-party-apps.md)」を参照してください。

## <a name="grant-permissions-and-consent-to-apps-to-use-end-user-information"></a>エンドユーザー情報を使用するためのアクセス許可と同意をアプリに付与する

組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認し、同意を付与することができます。 こうすることで、ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して受け入れる必要はなくなります。 "**アクセス許可**" 列は、アプリに同意が必要なアクセス許可があるかどうかを示します。 同意が必要なアクセス許可を持つAzure ADに登録されている各アプリの **[詳細の表示]** リンクが表示されます。 詳細については、「[Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する](app-permissions-admin-center.md)」を参照してください。

## <a name="view-resource-specific-consent-permissions"></a>リソース固有の同意のアクセス許可を表示する

リソース固有の同意 (RSC) アクセス許可を使用すると、チームの所有者は、アプリがチームのデータにアクセスして変更するための同意を付与できます。 RSC のアクセス許可は、アプリが特定のチームで何を実行できるかを定義する、粒度の細かい Teams 固有のアクセス許可です。 RSC のアクセス許可は、アプリの [アプリの詳細] ページの **[アクセス許可]** タブで表示できます。 詳細については、「[Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する](app-permissions-admin-center.md)」を参照してください。

## <a name="manage-org-wide-app-settings"></a>組織全体のアプリ設定の管理

組織全体のアプリ設定を使用して、 [F ライセンス](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) を持つユーザーがカスタマイズされた最前線のアプリ エクスペリエンスを利用できるかどうか、ユーザーがサード パーティのアプリをインストールできるかどうか、およびユーザーが組織内のカスタム アプリをアップロードまたは操作できるかどうかを制御します。 組織全体のアプリ設定は、すべてのユーザーの動作を管理し、ユーザーに割り当てられた他のアプリ権限ポリシーを上書きします。 それらを使用して、悪意のあるアプリや問題のあるアプリを制御できます。

> [!NOTE]
> Microsoft 365 Government - Government Community Cloud High GCCH および国防総省 (DoD) の Teams のデプロイで組織全体のアプリ設定を使用する方法については、「[Teams でアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」を参照してください。

1. [アプリの管理] ページで、**[組織全体のアプリ設定]** を選択します。 次に、パネルで必要な設定を構成できます。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="[アプリの管理] ページの [組織全体のアプリ設定] ウィンドウを示すスクリーンショット":::

1. [ **カスタマイズされたアプリ**] で、[ **カスタマイズした** アプリの表示] をオフまたはオンにします。 この設定をオンにすると、 [F ライセンスを持つユーザー](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)は、カスタマイズされた現場アプリのエクスペリエンスを利用できます。 このエクスペリエンスにより、現場担当者にとって Teams で最も関連性の高いアプリがピン留めされます。 詳細については、「[現場担当者向けに Teams アプリを調整する](pin-teams-apps-based-on-license.md)」を参照してください。

    この機能は F ライセンスで使用できます。 その他のライセンスの種類は、今後サポートされる予定です。
1. **[サードパーティ アプリ]** で、次の設定をオフまたはオンにして、サードパーティ アプリへのアクセスを制御します。

    * **[サードパーティ アプリを許可する]**: ここで、ユーザーがサードパーティ アプリを使用できるかどうかを制御します。 この設定をオフにした場合、ユーザーはサードパーティ製アプリをインストールまたは使用できず、これらのアプリのアプリ状態は、"**組織全体でブロック**" としてテーブルに表示されます。

        > [!NOTE]
        > **[サードパーティ製アプリのを許可]** がオフの場合、[送信 Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) は引き続きすべてのユーザーに対して有効になりますが、[[アプリのアクセス許可ポリシー]](teams-app-permission-policies.md) を使用して送信 Webhook アプリを許可またはブロックすることで、ユーザー レベルの制御ができます。 **[特定のアプリを許可し、他のすべてをブロックする]** 設定を使用する **Microsoft アプリ** に対して既存の [アプリアクセス許可ポリシー](teams-app-permission-policies.md)があり、ユーザーに対して送信 Webhook を有効にする場合は、送信 Webhook アプリを一覧に追加します。

        > [!NOTE]
        > Teams ユーザーは、他の組織のユーザーとの会議やチャットをホストするときにアプリを追加できます。 他の組織がホストする会議やチャットに参加するときに、他の組織のユーザーが共有するアプリを使用することもできます。 ホストしているユーザーの組織のデータ ポリシーと、そのユーザーの組織が共有するサードパーティ アプリのデータ共有の慣行が適用されます。

    * **ストアに公開された新しいサードパーティ アプリを既定で許可する**: ここでは、Teams アプリ ストアに公開された新しいサードパーティ アプリを Teams で自動的に利用可能にするかどうかを制御します。このオプションは、サードパーティのアプリを許可する場合にのみ設定できます。

1. **[カスタム アプリ]** で、**[カスタム アプリとの対話を許可する]** をオフまたはオンにします。 この設定は、ユーザーがカスタム アプリを操作できるかどうかを制御します。 詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」をご覧ください。
1. 組織全体のアプリ設定を有効にするには、**[保存]** を選択します。

## <a name="see-also"></a>関連項目

* [Skype for Business管理センターからの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
