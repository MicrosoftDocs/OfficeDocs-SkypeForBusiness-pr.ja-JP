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
ms.openlocfilehash: 9790cfb186e1745d7233bf23232ac4b4a69b00e0
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997325"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)。

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Microsoft 365 グループの作成が可能になっている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの画像の変更 (Outlook on the web メールボックス ポリシーで許可されている場合)、コネクタやタブ、ボットの追加と構成を行うことができます。 利用可能な機能のより包括的なリストについては、以下の表を参照してください。

Exchange Online 専用 (レガシ) にホストされるユーザーは、Microsoft 365 や Office 365 の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、これらのユーザーは、プロフィール画像を変更したり、会議を管理したり、Outlook の連絡先にアクセスしたり、コネクタを管理したりできません。

> [!IMPORTANT]
> オンプレミスと統合するには、Exchange Server 2016 以降で Exchange の完全なクラシック ハイブリッド展開を行うことを強くお勧めします。 最新のハイブリッド サポートは空き時間情報に限定されており、たとえば、チームからオンプレミスのメールボックスへのカレンダー統合は提供されません。 ハイブリッド展開の設定の詳細については、「[Exchange Server Hybrid Deployments](https://docs.microsoft.com/exchange/exchange-hybrid)」を参照してください。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオのすべての機能を利用できますが、さらに、[オンプレミスでホストされるメールボックスの要件](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)のセクションに記載されている要件が満たされている場合は、会議を管理できます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先:                                        | 電子情報開示       | 法的な&nbsp;保全    | 保持  | チームとチャネルの管理 | Teams で会議を作成して表示する | ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール  | コネクタを追加して構成する | タブを追加して構成する | ボットを追加して構成する |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | はい <sup>1</sup> | はい <sup>1</sup>   | はい        | はい                   | はい                               | はい<sup>7</sup>             | はい          | はい             | はい <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 vNext**                                 | はい <sup>1</sup> | はい <sup>1</sup>   | はい        | はい                   | はい                               | はい<sup>7</sup>             | はい          | はい             | はい <sup>6</sup>        | はい        | はい                          | はい                    | はい                    |
| **Exchange Online 専用 – レガシー** (Azure AD との同期が必要)  | はい <sup>1</sup> | はい <sup>1,2</sup> | はい <sup>3</sup> | はい                   | いいえ                                | いいえ                          | はい          | はい             | 不要                      | はい <sup>4</sup> | はい <sup>5</sup>                   | はい                    | はい                    |
| **Exchange On-premises** (Azure AD との同期) | ○ <sup>1,9</sup> | はい <sup>1</sup>   | はい <sup>3</sup> | はい                   | はい <sup>8</sup>         | いいえ                          | はい          | はい             | 不要                      | はい <sup>4</sup> | はい <sup>5</sup>                   | はい                    | はい                    |

<sup>1</sup> チャネル メッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティング オプションでサポートされています。

<sup>2</sup> Teams のプライベート チャット メッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>3</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウ メールボックスを使用します。

<sup>4</sup> オンプレミスの Exchange メールボックスを使っている Teams ユーザーは、Teams でボイスメールを使用して Outlook でボイスメール メッセージを受信できますが、ボイスメール メッセージを Teams クライアント内で表示または再生することはできません。

<sup>5</sup> チームの所有者の 1 人がコネクタを追加できる場合、そのチーム内のすべてのユーザーは、メールボックスがオンプレミスであったとしても、その操作を行うことができます。

<sup>6</sup> 既定の連絡先フォルダーは連絡先のみです。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

<sup>7</sup> Teams では、ユーザーがプロフィール画像を変更できるかどうかを制御するため、テナント管理者によって構成されている[Outlook on the web のメールボックス ポリシー](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)の設定を優先します。 **ポリシーで -SetPhotoEnabled** 設定がオフになっている場合、ユーザーはプロファイル画像を追加、変更、または削除できないので、管理者が写真を変更した場合、porfile 画像はチームに同期されません。
<sup>8</sup> 「[オンプレミスでホストされているメールボックスの会議を作成および表示するための要件](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)」セクション記載されている要件を満たす必要があります。 

<sup>9</sup> 最低でも Exchange Online プラン 1 のライセンスが必要です。 詳細については、「オンプレミス ユーザーの Teams チャット データを検索 [する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams では、Microsoft 365 や Office 365 のさまざまなサービスにより、ユーザーに高度なエクスペリエンスを提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- ユーザーには Exchange Online ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーに SharePoint Online の有効なライセンスが割り当てられていない場合は、Microsoft 365 やOffice 365 に OneDrive for Business のストレージがありません。 ファイル共有はチャネル内で引き続き動作しますが、Microsoft 365 やOffice 365 に OneDrive for Business ストレージがないと、ユーザーはチャットでファイルを共有することができません。

- ユーザーが Microsoft Teams でチームを作成するためには、Microsoft 365 グループの作成について有効になっている必要があります。

  > [!IMPORTANT]
  > ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロフィール画像を選択し、**[設定]** を選択します。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>オンプレミスでホストされているメールボックスの会議を作成および表示するための要件

メールボックスがオンプレミスでホストされている場合、会議を作成および表示するには、次の要件を満たす必要があります。

- 必要な Teams ライセンスは、Azure Active Directory 同期ユーザーに割り当てる必要があります。

- ユーザーは、Azure Active Directory と同期する必要があります。 Azure AD Connect を使用して Azure Active Directory と同期する方法については、「[ハイブリッド ID ドキュメント](https://docs.microsoft.com/azure/active-directory/hybrid/)」を参照してください。

- メールボックスは、Exchange Server 2016 累積的更新プログラム 3 以降でホストされます。

- 自動検出および Exchange Web サービスは外部に公開されています。

- OAuth 認証は、完全なハイブリッド構成 (クラシックまたはモダン) を実行する Exchange ハイブリッド構成ウィザードを介して構成することが望ましいです。 ハイブリッド構成ウィザードを使用できない場合は、「[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従ってOAuth を構成します。

  > [!NOTE]
  > Exchange は、EvoSTS として知られる Teams サービスからの OAuth トークンを信頼します。 手順 1 で十分ですが、EvoSTS だけで、ACS はカレンダーの空き時間情報の検索に使用されます。

- Azure AD Connect の Exchange ハイブリッド展開機能のチェックボックスが設定されています。

- カレンダー アプリのサポートと Mac 用の Teams Outlook アドインの場合、Exchange Web サービスの URL を Exchange サービス プリンシパルのテナント Azure AD で SPN として構成する必要があります。 この手順は、ハイブリッド構成ウィザードを使用するか、[手動でのハイブリッド先進認証の手順](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)に従って実行します。

これらのユーザーのカレンダー委任を有効にするには、

- 「Skype for Business Online と Skype for Business Online 間の統合と OAuth の構成」の説明に従って、手順 [を完了Exchange Server。](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)次の手順では、Teams のスケジュール アプリケーションに、代理人のアクセス許可を確認するために必要なアクセス許可が提供されます。
 
  > [!NOTE]
  > 手順 2 には、委任に必要のない ArchiveApplication の役割の割り当てが含まれています。

- Outlook 用 Teams スケジュール アドインでは、他のユーザーの代わりに会議をスケジュールする際に Exchange 2013 CU19 以降が必要です。 これは、委任メールボックスに対する委任権限をチェックするために、サービスによるメールボックスの認証されていない検出をサポートするためです。 代理人と代理人の場所は、Exchange 2013 以降、または Exchange オンラインですが、自動検出は Exchange 2013 CU19 以降に解決する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。 詳細については、「[プライベート ミーティングのスケジュールを許可する](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings)」をご覧ください。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「[オンプレミス ユーザーのクラウドベース メールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。 Teams でコンテンツを検索する方法については、「[Microsoft 365 コンプライアンス センターのコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)」を参照してください。

- プレゼンス ステータスについては、Microsoft Teams はメールボックスが Exchange Online でホストされているかオンプレミスでホストされているかを確認する必要があります。 次に、サービスはメールボックスにアクセスする場所を決定します。 Teams サービスが Exchange Online サービスへの REST API 呼び出しを介してメールボックスの場所を確認できるようにするには、「[ハイブリッド構成ウィザードを使用したハイブリッド展開の作成](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid)」で説明されているように、Exchange ハイブリッド構成ウィザードを実行してExchange ハイブリッド環境を展開する必要があります。

## <a name="troubleshooting"></a>トラブルシューティング

このトピックに関する完全なトラブルシューティングガイドについては、「[Microsoft Teams と Exchange Server の相互作用の問題のトラブルシューティング](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)」を確認してください。
