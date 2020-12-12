---
title: Exchange と Microsoft Teams の連携
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2e6af198c578279e2af8928e8a6ac299f262a5
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49661902"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> 次のセッションを見て、Teams が Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、OneDrive for Business とやり取りする方法について説明します[。Microsoft Teams](https://aka.ms/teams-foundations)の基礎

Teams のすべての機能を利用するには、すべてのユーザーが Exchange Online、SharePoint Online、Microsoft 365 グループの作成を有効にする必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 チームとチャネルの作成と参加、会議の作成と表示、通話とチャット、ユーザー プロファイル画像の変更 (Outlook on the web メールボックス ポリシーで許可されている場合)、コネクタ、タブ、ボットの追加と構成を行えます。 使用できる機能のより包括的なリストについては、次の表を参照してください。

Exchange Online Dedicated (レガシ) でホストされているユーザーは、Microsoft 365 または Office 365 の Azure Active Directory に同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、プロファイル画像の変更、会議の管理、Outlook の連絡先へのアクセス、コネクタの管理は行できません。

> [!IMPORTANT]
> オンプレミスと統合するには、2016 以降の Exchange Server との完全なクラシック ハイブリッド展開を Exchange を使用することを強くお勧めします。 最新のハイブリッド サポートは空き時間情報に制限され、たとえば Teams からオンプレミスのメールボックスに予定表を統合することはできません。 ハイブリッド展開のセットアップの詳細については、ハイブリッド展開の詳細Exchange Server [参照してください](https://docs.microsoft.com/exchange/exchange-hybrid)。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオですべての機能を利用できますが、また、オンプレミスでホストされるメールボックスの要件セクションに記載されている要件が満たされた[](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)場合は、会議を管理できます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先:                                        | 電子情報開示       | 法的な&nbsp;保全    | 保持  | チームとチャネルの管理 | Teams で会議を作成して表示する | ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール  | コネクタを追加して構成する | タブを追加して構成する | ボットを追加して構成する |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい        | はい                   | はい                               | ○<sup>7</sup>             | はい          | はい             | ○ <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 vNext**                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい        | はい                   | はい                               | ○<sup>7</sup>             | はい          | はい             | ○ <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 – レガシー** (Azure AD との同期が必要)  | ○ <sup>1</sup> | ○ <sup>1,2</sup> | はい <sup>3</sup> | はい                   | いいえ                                | いいえ                          | はい          | はい             | いいえ                      | はい <sup>4</sup> | ○ <sup>5</sup>                   | はい                    | はい                    |
| **Exchange オンプレミス** (Azure AD と同期) | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい <sup>3</sup> | はい                   | ○ <sup>8</sup>         | いいえ                          | はい          | はい             | いいえ                      | はい <sup>4</sup> | ○ <sup>5</sup>                   | はい                    | はい                    |

<sup>すべてのホスティング</sup> オプションで、チャネル メッセージのコンプライアンスに関する 1 つの電子情報開示と法的ホールドがサポートされています。

<sup>2</sup> つの Teams のプライベート チャット メッセージは、このホスティング オプションの法的ホールドではまだサポートされていません。

<sup>3</sup> アイテム保持では、オンライン ユーザーがメッセージを保存するために影のメールボックスを使用します。

<sup>4</sup> オンプレミスの Exchange メールボックスを持つ Teams ユーザーは、Teams でボイスメールを使用し、Outlook でボイスメール メッセージを受信できますが、ボイスメール メッセージは Teams クライアント内で表示または再生することはできません。

<sup>5</sup> チームの所有者の 1 人がコネクタを追加できる場合、メールボックスがオンプレミスに自宅に入っている場合でも、そのチームの他のすべてのユーザーがコネクタを追加できます。

<sup>6 既定</sup> の連絡先フォルダーの連絡先のみ。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

<sup>7</sup> Teams は、ユーザーがプロファイル画像を変更できるかどうかを制御するためにテナント管理者によって構成された [Outlook on the web](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) メールボックス ポリシー設定に適用されます。 ポリシーで **-SetPhotoEnabled** 設定がオフになっている場合、ユーザーはプロファイル画像を追加、変更、または削除することはできません。 たとえば、ユーザーが組織の IT 部門または人事部門によって承認されたプロファイル画像をアップロードした場合、何もする必要はありません。 ただし、ユーザーが不適切な画像をアップロードした場合は、組織の内部ポリシーに従って写真を変更します。

<sup>8</sup> オンプレミスでホストされるメールボックスの会議を作成して表示するには、「要件」セクションに記載されている要件 [を満たす必要](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) があります。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams は、複数の Microsoft 365 および Office 365 サービスと組み合って、豊富なエクスペリエンスをユーザーに提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- ユーザーには Exchange Online ライセンスが割り当てられている必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーが SharePoint Online ライセンスで割り当てられていない、有効になっていない場合は、Microsoft 365 または Office 365 に OneDrive for Business ストレージはありません。 ファイル共有はチャネルで引き続き機能しますが、Microsoft 365 または Office 365 の OneDrive for Business ストレージがない場合、ユーザーはチャットでファイルを共有できません。

- Microsoft Teams でチームを作成するには、ユーザーが Microsoft 365 グループの作成を有効にする必要があります。

  > [!IMPORTANT]
  > ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロフィール画像を選択し、**[設定]** を選択します。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>オンプレミスでホストされるメールボックスの会議を作成および表示する要件

メールボックスがオンプレミスでホストされている場合、会議を作成して表示するには、次の要件を満たす必要があります。

- Azure Active Directory 同期ユーザーに必要な Teams ライセンスを割り当てる必要があります。

- ユーザーは Azure Active Directory と同期する必要があります。 Azure Active Directory と同期するために Azure ADを使用する方法については、ハイブリッド ID ドキュメント [を参照してください](https://docs.microsoft.com/azure/active-directory/hybrid/)。

- メールボックスは、Exchange Server 2016 累積更新プログラム 3 以降でホストされます。

- 自動検出と Exchange Web サービスは外部に公開されます。

- OAuth 認証は、完全なハイブリッド構成 (クラシックまたはモダン) を実行する Exchange ハイブリッド構成ウィザードを使用して構成することが望ましいです。 ハイブリッド構成ウィザードを使用できない場合は、「Exchange と Exchange Online の組織間で OAuth 認証を構成する」の説明に従って [OAuth を構成します](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。

  > [!NOTE]
  > Exchange は、EvoSTS と呼ばれる Teams サービスからの OAuth トークンを信頼します。 手順 1 で十分ですが、EvoSTS だけで十分です。ACS は、予定表での空き時間情報の参照に使用されます。

- Azure AD Connect の Exchange ハイブリッド展開機能のチェック ボックスが設定されています。

- 予定表アプリのサポートと Teams Outlook Add-In for Mac の場合、Exchange サービス プリンシパルのテナント Azure AD で Exchange Web サービスの URL を SPN として構成する必要があります。 この手順は、ハイブリッド構成ウィザードまたはハイブリッドモダン認証の手動 [手順に従って行います](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)。

これらのユーザーに対して予定表の委任を有効にするには、次の手順を実行します。

- 「Skype for Business Online と Skype for Business Online の間で統合と OAuth を構成する」の説明に従って、手順 2 から 3 [を完了Exchange Server。](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)次の手順では、Teams のスケジュール アプリケーションに、代理人のアクセス許可を確認するために必要なアクセス許可が提供されます。
 
  > [!NOTE]
  > 手順 2 には ArchiveApplication の役割の割り当てが含まれています。これは委任には必要ありません。

- 他のユーザーの代わりに会議をスケジュールする際に Outlook 用 Teams スケジュール アドインを使用するには、Exchange 2013 CU19 以降が必要です。 これは、委任者メールボックスに対する代理人のアクセス許可を確認するために、サービスによってメールボックスが認証されていない検出をサポートするための方法です。 代理人と委任者の場所は Exchange 2013 以降、または Exchange Online の場合がありますが、自動検出は Exchange 2013 CU19 以降に解決する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。 詳細については、「プライベート会議の [スケジュール設定を許可する」を参照してください](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「オンプレミス ユーザー [のクラウド ベースのメールボックスを検索する」を参照してください](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)。 Teams でコンテンツを検索する方法については [、Microsoft 365](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)コンプライアンス センターのコンテンツ検索を参照してください。

- プレゼンス状態の場合、Microsoft Teams はメールボックスが Exchange Online またはオンプレミスでホストされているかどうかを確認する必要があります。 その後、サービスはメールボックスにアクセスする場所を決定します。 Teams サービスが Exchange Online サービスへの REST API 呼び出しを通じてメールボックスの場所を確認するには、「ハイブリッド構成ウィザードを使用してハイブリッド展開を作成[](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)する」の説明に従って、Exchange ハイブリッド構成ウィザードを実行して Exchange ハイブリッド環境を展開する必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

このトピックに関する完全なトラブルシューティング ガイドについては [、「Microsoft Teams](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)のトラブルシューティングと対話に関する問題Exchange Server確認してください。
