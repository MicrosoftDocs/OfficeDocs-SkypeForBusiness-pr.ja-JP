---
title: Exchange と Microsoft Teams の連携
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a753e572cc9427a4b128379b52562437f739bea
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019403"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teams の基礎](https://aka.ms/teams-foundations)。

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Microsoft 365 グループの作成が可能になっている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの画像の変更 (Outlook on the web メールボックス ポリシーで許可されている場合)、コネクタやタブ、ボットの追加と構成を行うことができます。 利用可能な機能のより包括的なリストについては、以下の表を参照してください。

Exchange Online 専用 (レガシ) にホストされるユーザーは、Microsoft 365 や Office 365 の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、これらのユーザーは、プロフィール画像を変更したり、会議を管理したり、Outlook の連絡先にアクセスしたり、コネクタを管理したりできません。

> [!IMPORTANT]
> オンプレミスと統合するには、Exchange Server 2016 以降で Exchange の完全なクラシック ハイブリッド展開を行うことを強くお勧めします。 最新のハイブリッド サポートは空き時間情報に限定されており、たとえば、チームからオンプレミスのメールボックスへのカレンダー統合は提供されません。 ハイブリッド展開の設定の詳細については、「[Exchange Server Hybrid Deployments](/exchange/exchange-hybrid)」を参照してください。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオのすべての機能を利用できますが、さらに、[オンプレミスでホストされるメールボックスの要件](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)のセクションに記載されている要件が満たされている場合は、会議を管理できます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先:                                       | 電子情報開示         | 法的な&nbsp;保全    | 保持        | チームとチャネルの管理 | Teams で会議を作成して表示する | ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール        | コネクタを追加して構成する | タブを追加して構成する | ボットを追加して構成する | 不在時の設定を変更する |
|--------------------------------------------------------------------|--------------------|--------------------|------------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------------|------------------------------|------------------------|------------------------|------------------------|
| **Exchange Online**                                                | はい <sup>1</sup>   | はい <sup>1</sup>   | はい              | Yes                   | Yes                               | はい<sup>7</sup>             | はい          | Yes             | はい <sup>6</sup>        | はい              | Yes                          | Yes                    | Yes                    | Yes                    
| **Exchange Online 専用 vNext**                                | はい <sup>1</sup>   | はい <sup>1</sup>   | はい              | Yes                   | Yes                               | はい<sup>7</sup>             | はい          | Yes             | はい <sup>6</sup>        | はい              | Yes                          | Yes                    | Yes                    | Yes                    
| **Exchange Online 専用 – レガシー** (Azure AD との同期が必要) | はい <sup>1</sup>   | はい <sup>1,2</sup> | はい <sup>3</sup> | はい                   | いいえ                                | いいえ                          | Yes          | Yes             | いいえ                      | はい <sup>4</sup> | はい <sup>5</sup>             | はい                    | Yes                    | Yes                    
| **Exchange On-premises** (Azure AD との同期)                        | はい <sup>1,9</sup> | はい <sup>1</sup>   | はい <sup>3</sup> | はい                   | はい <sup>8</sup>                  | はい<sup>10</sup>            | Yes          | Yes             | いいえ                      | はい <sup>4</sup> | はい <sup>5</sup>             | はい                    | Yes                    | いいえ                      

<sup>1</sup> チャネル メッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティング オプションでサポートされています。

<sup>2</sup> Teams のプライベート チャット メッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>3</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウ メールボックスを使用します。

<sup>4</sup> オンプレミスの Exchange メールボックスを使っている Teams ユーザーは、Teams でボイスメールを使用して Outlook でボイスメール メッセージを受信できますが、ボイスメール メッセージを Teams クライアント内で表示または再生することはできません。

<sup>5</sup> チームの所有者の 1 人がコネクタを追加できる場合、メールボックスがオンプレミスかオンラインかに関係なく、そのチームの他のすべてのユーザーがコネクタを追加できるようになります。

<sup>6</sup> 既定の連絡先フォルダーは連絡先のみです。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

<sup>7</sup> Teams では、ユーザーがプロフィール画像を変更できるかどうかを制御するため、テナント管理者によって構成されている[Outlook on the web のメールボックス ポリシー](/powershell/module/exchange/client-access/set-owamailboxpolicy)の設定を優先します。 ポリシーで **-SetPhotoEnabled** 設定がオフになっている場合、ユーザーはプロフィール画像を追加、変更、または削除できないため、管理者が写真を変更した場合、プロファイル画像はチームに同期されません。

<sup>8</sup> 「[オンプレミスでホストされているメールボックスの会議を作成および表示するための要件](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises)」セクション記載されている要件を満たす必要があります。 

<sup>9</sup> Exchange Online プラン 1 ライセンスの最小値も必要です。 詳細については、「 [オンプレミス ユーザーの Teams チャット データを検索する](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。

<sup>10</sup> オンプレミス ユーザーは、Outlook on the Web メールボックス ポリシーが に設定されている場合 `SetPhotoEnabled` でも、Teams を使用してプロファイル画像を `false`更新できます。
 > [!NOTE]
 > Teams クライアント経由での Out of Office (OOF) の設定は、現在、メールボックスがオンプレミスでホストされているユーザーではサポートされていません。これらのユーザーは、Outlook クライアントを使用してこのアクションを実行する必要があります。
## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams では、Microsoft 365 や Office 365 のさまざまなサービスにより、ユーザーに高度なエクスペリエンスを提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- ユーザーには Exchange Online ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーに SharePoint Online の有効なライセンスが割り当てられていない場合は、Microsoft 365 やOffice 365 に OneDrive for Business のストレージがありません。 ファイル共有はチャネル内で引き続き動作しますが、Microsoft 365 やOffice 365 に OneDrive for Business ストレージがないと、ユーザーはチャットでファイルを共有することができません。

- ユーザーが Microsoft Teams でチームを作成するためには、Microsoft 365 グループの作成について有効になっている必要があります。

  > [!IMPORTANT]
  > ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロファイル画像の左側にある省略記号ボタンを選択し、[設定] を選択 **します**。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>オンプレミスでホストされているメールボックスの会議を作成および表示するための要件

  > [!NOTE]
  > **オンプレミスでホストされているメールボックスの会議の作成と表示** 機能は、商用、GCC、GCC High 環境でのみサポートされます。

メールボックスがオンプレミスでホストされている場合、会議を作成および表示するには、次の要件を満たす必要があります。

- 必要な Teams ライセンスは、Azure Active Directory 同期ユーザーに割り当てる必要があります。

- ユーザーは、Azure Active Directory と同期する必要があります。 Azure AD Connect を使用して Azure Active Directory と同期する方法については、「[ハイブリッド ID ドキュメント](/azure/active-directory/hybrid/)」を参照してください。

- メールボックスは、Exchange Server 2016 累積的更新プログラム 3 以降でホストされます。

- 自動検出と Exchange Web サービスは外部で公開されます。 オンプレミスの自動検出および Exchange Web サービス エンドポイントへのアクセスが必要な Microsoft 365 サービスの詳細については、「[Office 365 IP アドレスと URL Web サービスに含まれていないその他のエンドポイント」を](/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls)参照してください。

- OAuth 認証は、完全なハイブリッド構成 (クラシックまたはモダン) を実行する Exchange ハイブリッド構成ウィザードを介して構成することが望ましいです。 ハイブリッド構成ウィザードを使用できない場合は、「[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従ってOAuth を構成します。

  > [!NOTE]
  > Exchange は、EvoSTS として知られる Teams サービスからの OAuth トークンを信頼します。 手順 1 で十分ですが、EvoSTS だけで、ACS はカレンダーの空き時間情報の検索に使用されます。

- Azure AD Connect の Exchange ハイブリッド展開機能のチェックボックスが設定されています。 詳細については、「 [Exchange ハイブリッド ライトバック](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#exchange-hybrid-writeback)」を参照してください。

- カレンダー アプリのサポートと Mac 用の Teams Outlook アドインの場合、Exchange Web サービスの URL を Exchange サービス プリンシパルのテナント Azure AD で SPN として構成する必要があります。 この手順は、ハイブリッド構成ウィザードを使用するか、[手動でのハイブリッド先進認証の手順](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad)に従って実行します。

これらのユーザーのカレンダー委任を有効にするには、

- また、「[Skype for Business Online と Exchange Server間の統合と OAuth の構成](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」の説明に従って手順を完了する必要があります。これらの手順では、Teams スケジュール アプリケーションに委任アクセス許可を確認するために必要なアクセス許可が提供されます。
 
  > [!NOTE]
  > 手順 2 には、委任に必要のない ArchiveApplication の役割の割り当てが含まれています。

- Outlook 用 Teams スケジュール アドインでは、他のユーザーに代わって会議をスケジュールするときに Exchange 2013 CU19 以降が必要です。 これは、委任メールボックスに対する委任権限をチェックするために、サービスによるメールボックスの認証されていない検出をサポートするためです。 代理人と代理人の場所は、Exchange 2013 以降、または Exchange オンラインですが、自動検出は Exchange 2013 CU19 以降に解決する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- In Microsoft Teams, security and compliance features like eDiscovery, Content Search, archiving, and legal hold work best in Exchange Online and SharePoint Online environments. For channel conversations, messages are journaled to the group mailbox in Exchange Online, where they're available for eDiscovery. If SharePoint Online and OneDrive for Business (using work or school account) are enabled across the organization and for users, these compliance features are available for all files within Teams as well.

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。 詳細については、「 [プライベート会議のスケジュール設定](./meeting-policies-in-teams-general.md#private-meeting-scheduling)」を参照してください。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「[オンプレミス ユーザーのクラウドベース メールボックスの検索](/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。 Teams でコンテンツを検索する方法については、[Microsoft Purview コンプライアンス ポータルのコンテンツ検索に関するページを参照してください](/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)。

- プレゼンス ステータスについては、Microsoft Teams はメールボックスが Exchange Online でホストされているかオンプレミスでホストされているかを確認する必要があります。 次に、サービスはメールボックスにアクセスする場所を決定します。 Teams サービスが Exchange Online サービスへの REST API 呼び出しを介してメールボックスの場所を確認できるようにするには、「[ハイブリッド構成ウィザードを使用したハイブリッド展開の作成](/exchange/hybrid-deployment/deploy-hybrid)」で説明されているように、Exchange ハイブリッド構成ウィザードを実行してExchange ハイブリッド環境を展開する必要があります。

>[!Important]
>**GCC-H のお客様:** *委任された Teams 会議スケジュール* は、ユーザーのメールボックスがオンプレミスのExchange Serverでホストされている場合、GCC-High環境ではサポートされていません。

## <a name="troubleshooting"></a>トラブルシューティング

このトピックに関する完全なトラブルシューティングガイドについては、「[Microsoft Teams と Exchange Server の相互作用の問題のトラブルシューティング](/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue)」を確認してください。
