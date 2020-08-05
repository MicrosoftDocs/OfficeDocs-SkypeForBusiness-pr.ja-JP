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
ms.openlocfilehash: 8b064fa34511704c382ca42e6daa7812c17a13b0
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552013"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> チームと Azure Active Directory (AAD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

完全なチームエクスペリエンスを実現するには、すべてのユーザーが Exchange Online、SharePoint Online、および Microsoft 365 グループの作成を有効にしている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。 オンプレミスの Exchange との統合には、Exchange ハイブリッド展開が必要です。 ハイブリッド展開のセットアップの詳細については、「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)」を参照してください。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 メンバーは、チームとチャネルの作成と参加、会議の作成と表示、電話とチャット、ユーザープロファイルの画像の変更 (Outlook on the web メールボックスポリシーで許可されている場合) の変更、コネクタ、タブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 (レガシ) でホストされているユーザーは、Microsoft 365 または Office 365 上の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、プロフィール画像の変更、会議の管理、outlook の連絡先へのアクセス、コネクタの管理はできません。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオのすべての機能を使うことができます。さらに、ユーザープロファイルの画像 (Outlook on the web メールボックスポリシーで許可されている場合) を変更することもできます。また、Exchange Server 2016 (累積更新プログラム 3) 以降を実行している場合は、「 [exchange と Exchange Online の間の oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」で説明されているように、oauth 構成 (Exchange ハイブリッド構成ウィザード これらのユーザーに対して予定表の委任を有効にするには、「 [Skype For Business Online と Exchange Server の間の統合と OAuth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明する手順2-3 を実行する必要があります。これらの手順では、チームのスケジュールアプリケーションに委任権限を確認するために必要な権限が与えられます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。

> [!NOTE]
> オンプレミスの Exchange と Teams の機能の統合には、Exchange ハイブリッド展開が必要です。 この要件は、次の表のいくつかの機能で利用されているバージョン固有の要件に加えています。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先:                                        | 電子情報開示       | 法的な&nbsp;保全    | 保持  | チームとチャネルの管理 | Teams で会議を作成して表示する | ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール  | コネクタを追加して構成する | タブを追加して構成する | ボットを追加して構成する |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | Yes        | Yes                   | Yes                               | ○ (<sup>7</sup> )             | Yes          | Yes             | はい<sup>6</sup>        | Yes        | Yes                          | Yes                    | Yes                    |
| **Exchange Online 専用 vNext**                                 | ○ <sup>1</sup> | ○ <sup>1</sup>   | Yes        | Yes                   | Yes                               | ○ (<sup>7</sup> )             | Yes          | Yes             | はい<sup>6</sup>        | Yes        | Yes                          | Yes                    | はい                    |
| **Exchange Online 専用 – レガシー** (Azure AD との同期が必要)  | ○ <sup>1</sup> | はい<sup>1、2</sup> | はい <sup> 3 | 必要                   | ×                                | いいえ                          | はい          | 必要             | いいえ                      | はい <sup>4 | はい <sup>5                   | はい                    | Yes                    |
| **Exchange on-premises** (Azure AD との同期 & OAuth 構成が必要) | ○ <sup>1</sup> | ○ <sup>1</sup>   | はい <sup> 3 | はい                   | はい (Exchange 2016 CU3+)          | いいえ                          | はい          | 必要             | いいえ                      | はい <sup>4 | はい <sup>5                   | はい                    | Yes                    |

チャネルメッセージのコンプライアンスのため<sup>の電子情報</sup>開示と法的保持は、すべてのホスティングオプションでサポートされています。

<sup>2</sup>チームプライベートチャットメッセージは、このホスティングオプションの法的保持に対してまだサポートされていません。

<sup>3</sup>保持は、オンラインユーザーがメッセージを保存するためのシャドウメールボックスを使います。

<sup>4</sup>オンプレミス Exchange メールボックスを使用している teams ユーザーは、Outlook でボイスメールを使用してボイスメールメッセージを受信することができます。ただし、ボイスメールメッセージは、teams クライアント内で表示または再生できません。

<sup>5</sup>チームの所有者の1人がコネクタを追加できる場合は、そのチーム内の他のすべてのユーザーがメールボックスをオンプレミスにしている場合でも、その操作を行うことができます。

[既定の連絡先] フォルダーの連絡先のみ<sup>6</sup> 。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

<sup>7</sup>チームは、テナント管理者によって構成された[web メールボックスのポリシー](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)設定を使用して、ユーザーが自分のプロファイル写真を変更できるかどうかを制御します。 ポリシーで **-setphotoenabled**設定が無効になっている場合、ユーザーはそのプロフィール画像を追加、変更、削除することはできません。 たとえば、ユーザーが組織の IT または人事部門によって承認されたプロファイル画像をアップロードした場合、操作は必要ありません。 ただし、ユーザーが不適切な画像をアップロードした場合は、組織の内部ポリシーに従って画像を変更します。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams は、さまざまな Microsoft 365 および Office 365 サービスと連携して、ユーザーに充実したエクスペリエンスを提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーが SharePoint Online ライセンスを割り当てて有効にしていない場合、Microsoft 365 または Office 365 の OneDrive for Business ストレージはありません。 ファイルの共有はチャネルでの作業を続けますが、Microsoft 365 または Office 365 では、OneDrive for Business の記憶域なしでチャットでファイルを共有することはできません。

- Microsoft Teams で teams を作成するには、Microsoft 365 グループの作成のためにユーザーを有効にする必要があります。

- Microsoft Teams で Exchange をオンプレミスで使用できるようにするには、exchange ハイブリッドウィザードを実行することで、可能であれば新しい Exchange OAuth 認証プロトコルを構成する必要があります。詳細については、「 [exchange と Exchange Online 組織の間の OAuth 認証を構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)する」を参照してください。 Exchange のオンプレミスメールボックスを使用してユーザーが別のユーザーの代わりにチーム会議をスケジュールできるようにするには、「 [Skype For Business Online と Exchange Server の間の統合と OAuth の構成](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)」で説明されている手順2-3 を完了する必要があります。

> [!NOTE]
> Outlook Teams アドインを使用して、オンプレミスの Exchange でホストされているメールボックスの Teams 会議をスケジュール設定することができます。 ただし、オンプレミスの Exchange を使用している他のユーザーに代わってチーム会議をスケジュールするには、Exchange 2013 CU9 以上と新しい Exchange OAuth 認証プロトコルが必要です。 代理人と委任者は両方とも Exchange on/オンプレミスのメールボックスを持っている必要があります。

> [!NOTE]
> Exchange On-premises と Teams を統合するには、必要なライセンスを AAD の同期されたユーザーに割り当てる必要があります。

> [!IMPORTANT]
> ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロフィール画像を選択し、**[設定]** を選択します。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください .

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「[オンプレミスユーザー向けのクラウドベースのメールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。 Teams でコンテンツを検索する方法については、 [Microsoft 365 コンプライアンスセンターでコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)を参照してください。

> [!TIP]
> Azure AD Connect を使用して Azure Active Directory と同期する方法については、「[オンプレミス ID と Azure Active Directory の統合](https://go.microsoft.com/fwlink/?linkid=854600)」を参照してください。

## <a name="requirements-for-on-premises-exchange-mailbox-user"></a>オンプレミスの Exchange メールボックスユーザーの要件

ユーザーが Exchange を使用して Teams の会議をスケジュールする機能を希望する場合は、次のことを確認する必要があります。

- 代理人と委任者は両方とも Exchange サーバー上にメールボックスを持っている必要があります。

- 自動検出 (AutoD) V2 は、Teams サービスがユーザーのメールボックスの認証されていない検出を実行できるようにするために必要です。 AutoD V2 は、Exchange 2013 CU19 + でサポートされています。

- Exchange サーバーを EVOSTS の Auth Server で構成する必要があります。 これは、Exchange (HWA) のハイブリッドウィザードの一部として自動的に構成されます。

    HWA を実行したくない場合は、次の手順に従って exchange[と Exchange Online 組織の間で OAuth 認証を構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)することにより、exchange SERVER で EVO STS の Auth サーバーを手動で作成することができます。 ただし、HWA を使用することをお勧めします。

- Exchange server には、Skype for Business online のアプリケーション ID を使って構成されたパートナーアプリケーションと **、00000004-0000-0ff1-ce00-000000000000**が含まれている必要があります。 ID は、チームスケジュールサービスと、次のプロパティを持つリンクされたユーザーアカウントによって使用されます。

  - Exchange のアドレス帳に表示されません。 無効なユーザーアカウントであるため、アドレス帳から非表示にすることをお勧めします。

  - **Userapplication**の Exchange 管理役割の割り当て。

統合を完了するには、「[オンプレミスの exchange と Exchange Online の間で OAuth 認証を構成する方法](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help#how-do-you-configure-oauth-authentication-between-your-on-premises-exchange-and-exchange-online-organizations)」の手順1-3 に従います。 手順2には、委任には必要ないアーカイブアプリケーションの役割の割り当てが含まれていますが、この場合は、SfB オンラインチャットを Exchange メールボックスにアーカイブする必要があります。
