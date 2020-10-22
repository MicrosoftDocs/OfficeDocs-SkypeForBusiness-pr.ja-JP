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
ms.openlocfilehash: ae03611a684f7f596c185873585c844e30d4330b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650880"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> チームと Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

完全なチームエクスペリエンスを実現するには、すべてのユーザーが Exchange Online、SharePoint Online、および Microsoft 365 グループの作成を有効にしている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 メンバーは、チームとチャネルの作成と参加、会議の作成と表示、電話とチャット、ユーザープロファイルの画像の変更 (Outlook on the web メールボックスポリシーで許可されている場合) の変更、コネクタ、タブ、ボットの追加と構成を行うことができます。 使用可能な機能の詳細な一覧については、以下の表を参照してください。

Exchange Online 専用 (レガシ) でホストされているユーザーは、Microsoft 365 または Office 365 上の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、プロファイル画像の変更、会議の管理、outlook の連絡先へのアクセス、コネクタの管理はできません。

> [!IMPORTANT]
> オンプレミスとの統合を実現するには、exchange Server 2016 以降を搭載した Exchange の完全な従来のハイブリッド展開を使用することを強くお勧めします。 モダンなハイブリッドサポートは空き時間情報に制限されています。たとえば、Teams から社内のメールボックスへの予定表の統合は提供されません。 ハイブリッド展開のセットアップの詳細については、「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)」を参照してください。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオではすべての機能を使用できますが、オンプレミスセクションでホストされている [メールボックスの要件](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) について記載されている要件が満たされている場合は、会議を管理することもできます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先:                                        | 電子情報開示       | 法的な&nbsp;保全    | 保持  | チームとチャネルの管理 | Teams で会議を作成して表示する | ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール  | コネクタを追加して構成する | タブを追加して構成する | ボットを追加して構成する |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい        | はい                   | はい                               | ○ (<sup>7</sup> )             | はい          | はい             | はい <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 vNext**                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい        | はい                   | はい                               | ○ (<sup>7</sup> )             | はい          | はい             | はい <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 – レガシー** (Azure AD との同期が必要)  | ○ <sup>1</sup> | はい <sup>1、2</sup> | はい <sup>3</sup> | はい                   | いいえ                                | いいえ                          | はい          | はい             | いいえ                      | はい <sup>4</sup> | ○ ( <sup>5</sup> )                   | はい                    | はい                    |
| **Exchange on-premises** (Azure AD との同期) | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい <sup>3</sup> | はい                   | ○ ( <sup>8</sup> )         | いいえ                          | はい          | はい             | いいえ                      | はい <sup>4</sup> | ○ ( <sup>5</sup> )                   | はい                    | はい                    |

チャネルメッセージのコンプライアンスのため<sup>の電子情報</sup>開示と法的保持は、すべてのホスティングオプションでサポートされています。

<sup>2</sup> チームプライベートチャットメッセージは、このホスティングオプションの法的保持に対してまだサポートされていません。

<sup>3</sup> 保持は、オンラインユーザーがメッセージを保存するためのシャドウメールボックスを使います。

<sup>4</sup> オンプレミス Exchange メールボックスを使用している teams ユーザーは、Outlook でボイスメールを使用してボイスメールメッセージを受信することができます。ただし、ボイスメールメッセージは、teams クライアント内で表示または再生できません。

<sup>5</sup> チームの所有者の1人がコネクタを追加できる場合は、そのチーム内の他のすべてのユーザーがメールボックスをオンプレミスにしている場合でも、その操作を行うことができます。

[既定の連絡先] フォルダーの連絡先のみ<sup>6</sup> 。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

<sup>7</sup> チームは、テナント管理者によって構成された [web メールボックスのポリシー](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy) 設定を使用して、ユーザーが自分のプロファイル写真を変更できるかどうかを制御します。 ポリシーで **-setphotoenabled** 設定を無効にした場合、ユーザーはそのプロフィール画像を追加、変更、削除することはできません。 たとえば、ユーザーが組織の IT または人事部門によって承認されたプロファイル画像をアップロードした場合、操作は必要ありません。 ただし、ユーザーが不適切な画像をアップロードした場合は、組織の内部ポリシーに従って変更します。

<sup>8</sup> [メールボックスがオンプレミスでホストされているメールボックスの会議を作成して表示するため](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) の要件を満たしている必要があります。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams は、さまざまな Microsoft 365 および Office 365 サービスと連携して、ユーザーに充実したエクスペリエンスを提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- ユーザーに Exchange Online ライセンスが割り当てられている必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーが SharePoint Online ライセンスを割り当てて有効にしていない場合、Microsoft 365 または Office 365 の OneDrive for Business ストレージはありません。 ファイルの共有はチャネルでの作業を続けますが、Microsoft 365 または Office 365 では、OneDrive for Business の記憶域なしでチャットでファイルを共有することはできません。

- Microsoft Teams で teams を作成するには、Microsoft 365 グループの作成のためにユーザーを有効にする必要があります。

  > [!IMPORTANT]
  > ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロフィール画像を選択し、**[設定]** を選択します。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>オンプレミスでホストされているメールボックスの会議を作成して表示するための要件

メールボックスがオンプレミスでホストされている場合、会議を作成して表示するには、次の要件を満たす必要があります。

- Azure Active Directory の同期されたユーザーに必要なチームライセンスを割り当てる必要があります。

- ユーザーを Azure Active Directory と同期する必要があります。 Azure AD Connect を使用して Azure Active Directory と同期する方法については、「 [ハイブリッド id のドキュメント](https://docs.microsoft.com/azure/active-directory/hybrid/)」を参照してください。

- メールボックスは Exchange Server 2016 累積更新プログラム3以降でホストされています。

- 自動検出と Exchange Web サービスは外部で公開されます。

- OAuth 認証は、完全なハイブリッド構成 (クラシックまたはモダン) を実行している Exchange ハイブリッド構成ウィザードで可能であることが推奨されます。 ハイブリッド構成ウィザードを使用できない場合は、「 [exchange と Exchange Online 組織の間での oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って oauth を構成します。

  > [!NOTE]
  > Exchange は EvoSTS と呼ばれる Teams サービスからの OAuth トークンを信頼します。 手順1で十分ですが、EvoSTS だけです。ACS は、予定表の空き時間情報を参照するために使用されます。

- Azure AD Connect の Exchange ハイブリッド展開機能のチェックボックスが設定されています。

- 予定表アプリのサポートと Teams Outlook Add-In for Mac の場合、exchange Web サービスの Url は、Exchange サービスプリンシパルのテナント Azure AD の Spn として構成されている必要があります。 この手順は、ハイブリッド構成ウィザードまたは [ハイブリッド先進認証の手動の手順](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)に従って行います。

次のユーザーに対して予定表の委任を有効にするには:

- また、「 [Skype For Business Online と Exchange Server の間の統合と OAuth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明する手順2-3 を実行する必要があります。これらの手順では、チームのスケジュールアプリケーションに委任権限を確認するために必要な権限が与えられます。
 
  > [!NOTE]
  > 手順2には、委任に必要ないアーカイブアプリケーションの役割の割り当てが含まれています。

- 他のユーザーの代わりに会議をスケジュールする場合の、Outlook 用の Teams のスケジュール設定 Exchange 2013 CU19 以降が必要です。 これは、サービスによるメールボックスの認証されていない検出をサポートし、委任者メールボックスに対する代理人のアクセス許可を確認することです。 代理人と委任者の場所は Exchange 2013 以降、または Exchange online ですが、自動検出は Exchange 2013 CU19 以降に解決する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。 詳細については、「 [プライベート会議のスケジュールを設定する](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)」を参照してください。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「 [オンプレミスユーザー向けのクラウドベースのメールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。 Teams でコンテンツを検索する方法については、 [Microsoft 365 コンプライアンスセンターでコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

このトピックの完全なトラブルシューティングガイドについては、「 [Microsoft Teams および Exchange Server の相互作用の問題のトラブルシューティング](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)」を確認してください。
