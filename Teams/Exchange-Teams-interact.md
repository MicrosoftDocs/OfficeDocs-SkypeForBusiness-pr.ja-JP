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
ms.openlocfilehash: e147a300f628347b5e38837a3d277a78a4c593c4
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285749"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Office 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teamsの基礎](https://aka.ms/teams-foundations)。

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、Office 365 グループの作成が可能になっている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストできます。 ただし、一部の機能では、Office 365 テナントを使用してハイブリッド展開を行う必要があります。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの画像の変更、コネクタやタブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 (レガシ) にホストされるユーザーは、Office 365 の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、チャットや通話機能の利用が可能です。 ただし、これらのユーザーは、プロフィール画像を変更したり、会議を管理したり、Outlook の連絡先にアクセスしたり、コネクタを管理したりできません。

オンプレミスでホストされているメールボックスを使っているユーザーは、Azure Active Directory と同期する必要があります。 これらのユーザーは、上記のシナリオにあるすべての機能を使用できます。さらに、Exchange Server 2016 (累積的な更新プログラム 3) 以降をオンプレミスで実行している場合、ユーザー プロフィールの画像を変更したり、会議を管理したりすることもできます。

次の表では、Exchange 環境に基づいて、機能の可用性に関する役立つクイック リファレンスをまとめています。


**サポートされるアクション:**

| ユーザーのメールボックスのホスト先: | 電子情報開示| 法的な&nbsp;保全 | 保持| チームとチャネルの管理 |Teams で会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい <sup>2</sup>|はい <sup>2</sup>|はい|はい|はい|はい|はい|はい|はい <sup>7</sup>|はい|はい|はい|はい|
|**Exchange Online 専用 vNext**|はい <sup>2</sup>|はい <sup>2</sup>|はい|はい|はい|はい|はい|はい|はい <sup>7</sup>|はい|はい|はい|はい|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|はい <sup>2</sup>|はい <sup>2、3</sup>|はい <sup>4|はい|いいえ|いいえ|はい|はい|いいえ|はい <sup>5|はい <sup>6|必要|必要|
|**Exchange On-premises** (Azure AD との同期が必要)|はい <sup>2</sup>| はい <sup>2、3</sup> |はい <sup>4|はい|はい (Exchange 2016 CU3+)|はい (Exchange 2016 CU3+)|はい|はい|いいえ|はい <sup>5|はい <sup>6|必要|必要|

<sup>1</sup> Exchange 2016 CU3 以降がサポートされています。  

<sup>2</sup> チャネル メッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティング オプションでサポートされています。

<sup>3</sup> Teams のプライベート チャット メッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>4</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウ メールボックスを使用します。 [Microsoft Teams で、Teams ユーザーの電子情報開示が Exchange ハイブリッド環境でサポートされるようになりました](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup> オンプレミスの Exchange メールボックスを使っている Teams ユーザーは、Teams でボイスメールを使用して Outlook でボイスメール メッセージを受信できますが、ボイスメール メッセージを Teams クライアント内で表示または再生することはできません。

<sup>6</sup> チームの所有者の 1 人がコネクタを追加できる場合、そのチーム内のすべてのユーザーは、メールボックスがオンプレミスであったとしても、その操作を行うことができます。

<sup>7</sup> 既定の連絡先フォルダーは連絡先のみ。 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams では、さまざまな Office 365 サービスにより、ユーザーに高度なエクスペリエンスを提供します。 そのようなエクスペリエンスをサポートするには、特定の機能またはサービスを有効にして、ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有するには、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーに SharePoint Online の有効なライセンスが割り当てられていない場合は、Office 365 に OneDrive for Business のストレージがありません。 ファイル共有はチャネル内で引き続き動作しますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャットでファイルを共有することができません。

- ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

- Microsoft Teams を Exchange On-premises と共に使う場合は、「[Exchange と Exchange Online 組織の間の OAuth 認証を構成する](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って、新しい Exchange OAuth 認証プロトコルを構成する必要があります。

> [!NOTE]
>Exchange On-premises と Teams を統合するには、必要なライセンスを AAD の同期されたユーザーに割り当てる必要があります。

> [!IMPORTANT]
> ユーザーを **[Teams のみ]** モードにした後に Skype for Business クライアントをアンインストールすると、Outlook および Office アプリでプレゼンスが機能しなくなる場合があります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にあるプロフィール画像を選択し、**[設定]** を選択します。 **[アプリケーション]** の下にある **[一般]** タブの、**[Teams を Office 用のチャット アプリとして登録します (Office アプリケーションを再起動する必要があります)]** を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を開くと、プレゼンス情報が表示されます。

## <a name="additional-considerations"></a>その他の考慮事項

組織で Microsoft Teams を実装する際は、さらに次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams や Exchange のコンプライアンス ポリシーの構成を制御および保護します。 詳細については、「[Teams に条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)」を参照してください 。

- すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者に Exchange オンプレミス メールボックスがある場合は、プライベート会議を無効にする必要があります。

- Exchange ハイブリッド展開では、チャット参加者が使用するメールボックスがクラウド ベースかオンプレミスかにかかわらず、チャット メッセージのコンテンツは検索可能です。 詳細については、「[Office 365 でのオンプレミス ユーザーのクラウドベース メールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)」を参照してください。 Teams でコンテンツを検索する方法については、「[Office 365 セキュリティ/コンプライアンスセンターのコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)」を参照してください。

> [!TIP]
> Azure AD Connect を使用して Azure Active Directory と同期する方法については、「[オンプレミス ID と Azure Active Directory の統合](https://go.microsoft.com/fwlink/?linkid=854600)」を参照してください。
