---
title: Microsoft Teams で会議ロビーをバイパスできるユーザーを制御する
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Teams の会議ロビーを使用して、特定の会議参加者のみが会議に直接参加できるようにする方法について説明します。
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392739"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Microsoft Teams で会議ロビーをバイパスできるユーザーを制御する

Teams 会議ロビーは、会議の開催者、共同開催者、または発表者が会議を許可するまで、特定の種類の会議参加者が会議に参加できないようにする方法です。 参加者がロビーに移動すると、開催者、共同開催者、発表者に通知が表示され、会議への参加を許可するかどうかが選択できます。

Teams 管理センターのロビー設定を使用して、どの種類の会議参加者がロビーをバイパスできるか、どの参加者が会議に参加するまで待機する必要があるかの既定値を作成できます。 次の種類の参加者がロビーと対話する方法を制御できます。

- 会議の開催者と共同開催者
- 組織内のPeople
- ゲスト
- 信頼された組織でのPeople
- 匿名の参加者

会議に参加するユーザーの ID は、参加者が匿名でない限り、Microsoft 365 によって検証されます。 匿名の参加者は確認できません。

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>組織外のユーザーとの会議の前提条件

Teams には、組織外のユーザーが Teams と対話できるかどうかを制御するいくつかの設定があります。 組織外のユーザーが会議に参加するには、次の設定を有効にする必要があります。

- [ゲストが会議に](guest-access.md) 参加できるようにするには、Teams のゲスト アクセスを有効にする必要があります。
- 信頼された組織のユーザーが会議に参加するには、[外部アクセス](manage-external-access.md)を有効にする必要があります。 組織と外部組織の間の相互信頼を構成し、組織内の会議の開催者と外部組織の参加者が外部アクセスを有効にする必要があります。
- **匿名ユーザーはどちらも、会議** 会議の設定 (組織レベル) と会議ポリシーに参加できます (会議を作成している開催者の場合) は、匿名の参加者が会議に参加するために **オン** である必要があります。

これらの設定のいずれかがオフになっている場合、その種類の外部参加者は、ロビーの設定に関係なく会議に参加できません。

## <a name="overview-of-lobby-settings-and-policies"></a>ロビーの設定とポリシーの概要

次の表は、会議参加者がロビーとやり取りする方法に影響を与える Teams 会議ポリシーを示しています。

|Setting|説明|
|:------|:----------|
|**匿名ユーザーとダイヤルイン呼び出し元は、会議を開始できます**|これは、リーダーレス会議を許可する開催者ごとのポリシーです。 この設定は、匿名の参加者とダイヤルイン ユーザーが出席に検証済みの参加者なしで会議に参加できるかどうかを制御します。 この設定は、 **ロビーをバイパスできるユーザーが** **[すべてのユーザー**] に設定されている場合にのみ適用されます。 **匿名ユーザーが会議組織に参加できる** 場合、または [会議] 設定が **[オフ]** の場合、この設定はダイヤルインの発信者にのみ適用されます。 既定では、匿名ユーザーによる会議リンクの悪用を防ぐために、この設定はオフになっています。 <br><br> **オフ** の間、匿名の参加者とダイヤルイン ユーザーは、確認済みの参加者 (ダイヤルインオーガナイザーを含む) が会議に参加するまでロビーで待機します。この時点で、自動的に許可されます。 会議が開始されると、開催者が離れる場合でも、匿名の参加者とダイヤルイン ユーザーが自動的に通話に参加します。 <br><br> この設定が **[オン] の** 場合、匿名およびダイヤルインの参加者は、確認済みの参加者が出席せずに会議を開始して参加できます。|
|**Peopleダイヤルインはロビーをバイパスできます**|これは開催者単位のポリシーです。 この設定は、電話でダイヤルインするユーザーが会議に直接参加するか、ロビーで待機するかを制御します。 この設定が **[オフ]** の場合、ダイヤルイン ユーザーは、開催者、共同開催者、または発表者が会議に参加し、承認するまでロビーで待機します。 この設定が **[オン]** の場合、ダイヤルイン ユーザーはロビーを経由せずに会議に自動的に参加します。 ( **匿名ユーザーとダイヤルイン呼び出し元が会議を開始できる** 場合は **、** 会議が開始されるまでロビーで待機します)。|
|**ロビーをバイパスできるユーザー**|これは開催者単位のポリシーです。 この設定では、会議に直接参加する参加者の種類 (電話でダイヤルインする参加者を除く) と、開催者、共同開催者、発表者によって承認されるまでロビーで待機する参加者の種類を制御します。|

次の表は、[ **ロビーをバイパスできるユーザー** ] ポリシーの各オプションが *、各種類の会議参加者* にどのように影響するかを示しています。

|ポリシー値:|すべてのユーザー|自分の組織、信頼できる組織、およびゲストのユーザー|自分とゲストの組織のユーザー|自分の組織のユーザー|招待されたユーザーのみ|開催者と共同開催者のみ|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*開催者と共同開催者*|バイパス|バイパス|バイパス|バイパス|バイパス|バイパス|
|*組織内のPeople*|バイパス|バイパス|バイパス|バイパス|招待People送信または転送されたユーザーはバイパスされます。他のユーザーはロビーで待機します|ロビー|
|*ゲスト*|バイパス|バイパス|バイパス|ロビー|招待People送信または転送されたユーザーはバイパスされます。他のユーザーはロビーで待機します|ロビー|
|*信頼された組織でのPeople*|バイパス|バイパス|ロビー|ロビー|招待People送信または転送されたユーザーはバイパスされます。他のユーザーはロビーで待機します|ロビー|
|*匿名の参加者*|バイパス|ロビー|ロビー|ロビー|ロビー|ロビー|

**招待されたユーザーのみが、招待** を送信された、または招待が転送された検証済みの参加者にのみ適用されます。 配布グループの一部として追加されたユーザーは、ロビーで待機します。

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>組織が主催する会議でロビーをバイパスできるユーザーを選択する

上記の設定とポリシーは、Teams 管理センターで構成できます。 さまざまな状況で選択する設定のガイダンスについては、以下のセクションを参照してください。 会議ポリシーのしくみについては、「Microsoft [Teams での会議ポリシーの管理](/microsoftteams/meeting-policies-overview)」を参照してください。

> [!Important]
> 会議の開催者は、**Peopleダイヤルインでロビーをバイパスし、ロビーの設定をバイパス****できるユーザー** に対して選択した既定値を変更できます。 これらの設定を特定の値に適用する必要がある場合は、会議テンプレートまたは秘密度ラベル (Teams Premium 必須) を使用できます。  詳細については、「[機密性の高い会議用にMicrosoft Teams 会議ロビーを構成する](configure-lobby-sensitive-meetings.md)」を参照してください。

会議参加ポリシーとロビー ポリシーを設定するには
1. Teams 管理センターで、[ **会議** ] を展開し、[ **会議ポリシー**] を選択します。
1. 更新するポリシーを選択します。
1. [ **ゲスト&参加者** ] セクションで、変更する設定を更新します。
   - **匿名のユーザーが会議に参加できるようにする**
   - **匿名ユーザーが会議を開始できるようにする**
   - **ユーザーを自動的に許可** する (ロビーをバイパスできるユーザー)
   - **ダイヤルイン ユーザーはロビーをバイパスできます**

    ![Teams 管理センターの会議参加ポリシーとロビー ポリシーを示すスクリーンショット。](media/meeting-join-and-lobby-tac-settings.png)
1. **[保存]** を選択します。

変更が有効になるまでに最大 24 時間かかる場合があることに注意してください。

匿名会議へのアクセスを許可する場合は、[ **匿名ユーザーが会議会議に参加できる** ] 設定もオンになっていることを確認します。

匿名会議参加の組織全体の会議設定を設定するには
1. Teams 管理センターで、[ **会議** ] を展開し、[ **会議の設定**] を選択します。
1. [ **参加者** ] セクションで、[ **匿名ユーザーが会議に参加できる** ] を **[オン** ] または **[オフ**] に設定します。
    ![Teams 管理センターの会議参加とロビーの設定を示すスクリーンショット。](media/anonymous-users-can-join-meetings-org-setting.png)
1. **[保存]** を選択します。

## <a name="control-access-to-meetings-by-anonymous-participants"></a>匿名参加者による会議へのアクセスを制御する

匿名の参加者は、Microsoft 365 で確認できるアカウントにログインしていないため、匿名です。 これには、次のものが含まれます。

- 職場または学校アカウントを使用して Microsoft 365 にログインしていないPeople 
- ([外部アクセス](manage-external-access.md)で構成されている) 信頼されていない組織からのPeople。
- 信頼しているが、組織を信頼していない組織からのPeople

匿名の参加者が会議に完全に参加できないようにする場合は、匿名ユーザーが会議組織全体の会議に **参加できる設定を** オフにすることができます。 また、匿名ユーザーが会議会議に参加できるポリシーを使用して、特定の会議開催者の **匿名参加を** 無効にすることもできます。

匿名で参加するユーザーがロビーで待機する場合は、[ロビー会議を **バイパスできるユーザー** ] ポリシーを [ **すべてのユーザー**] を除く任意の設定に設定できます。 (この設定は、電話でダイヤルインするユーザーには影響しません)。

既定では、 **匿名ユーザーとダイヤルインの呼び出し元が会議を開始できる** ポリシーは **[オフ] です**。 つまり、確認済みの参加者がまだ会議を開始していない場合、匿名の参加者と電話で呼び出すユーザーは常にロビーで待機します。 匿名の参加者や電話で通話するユーザーが会議を開始できるようにする状況がある場合は、この設定をオンにすることができますが、オフにしておくことをお勧めします。  設定がオンの場合、未確認のアカウントを持つユーザーは、会議リンクを使用して予定外の時間に会議を行うなど、会議を開始できます。

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>電話でダイヤルインするユーザーによる会議へのアクセスを制御する

既定では、**Peopleダイヤルインはロビー ポリシーをバイパスできますが****、会議** の開催者は会議を設定するときにこれを変更できます。 ロビー ポリシーを **バイパスできるPeopleを** 更新するか、会議テンプレートを使用して特定の値を適用することで、既定値を変更できます。

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>ゲストと信頼できる組織のユーザーによる会議へのアクセスを制御する

組織外には、確認済みの参加者として会議に参加できる 2 種類のユーザーがあります。

- ゲスト - 組織内に [Azure Active Directory (Azure AD) B2B コラボレーション アカウント](/azure/active-directory/external-identities/what-is-b2b) を持つユーザー
- 外部アクセス ユーザー - Teams [の外部アクセス](manage-external-access.md)で定義されている信頼された組織に Azure AD アカウントを持つユーザー

組織外のすべての確認済み会議参加者がロビーで待機する場合は、[ロビーをバイパスできるユーザー] ポリシーを [**組織のPeople**] または [**開催者と共同開催者のみ**] (ゲストが開催者または共同開催者でない限り) に設定できます。 信頼された組織のユーザー (外部アクセス ユーザー) のみがロビーで待機する場合は、**組織とゲストのPeople** を選択できます。

## <a name="control-access-to-meetings-by-people-without-invitations"></a>招待なしで会議へのアクセスをユーザーが制御する

招待を持つユーザーのみが会議に直接参加し、他のすべての参加者がロビーで待機できるようにする場合は、[ **ロビーをバイパスできるユーザー** ] を [ **招待されたユーザーのみ**] に設定します。 (配布リスト経由で招待されたPeopleは含まれません)。

[ **招待されたユーザーのみ** ] 設定には、開催者によって直接招待された参加者だけでなく、招待が転送された検証済みの参加者が含まれます。 会議参加リンクを持っているが、招待自体と未確認 (匿名) 参加者ではないユーザーは含まれません。 彼らはロビーで待つ必要があります。

会議の開催者は、会議に直接招待されたユーザーのみが会議に出席する必要がある場合は、会議出席依頼の転送を無効にできます。

## <a name="control-access-to-meetings-by-non-organizers"></a>非開催者による会議へのアクセスを制御する

機密情報が共有されている会議がある場合、または規制要件の対象となる会議がある場合は、会議の開催者または共同開催者によって許可されるまで、すべての参加者にロビーで待機させる必要があります。 この場合、[ **ロビーをバイパスできるユーザー** ] を [ **開催者と共同開催者のみ]** に設定できます。

**ロビーをバイパスできるユーザー** は、会議の開催者が変更できる既定値のみを設定するため、この領域にコンプライアンス要件がある場合は、秘密度ラベルまたは会議テンプレートを使用して値を適用することを検討してください。 詳細については、「[機密性の高い会議用にMicrosoft Teams 会議ロビーを構成する](configure-lobby-sensitive-meetings.md)」を参照してください。

## <a name="set-meeting-policies-by-using-powershell"></a>PowerShell を使用して会議ポリシーを設定する

この記事で説明されている会議ポリシーを設定するには、 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) PowerShell コマンドレットと次のパラメーターを使用します。

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) :匿名ユーザーが会議に参加できるかどうかを制御する
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) 電話でダイヤルインしているユーザーがロビーをバイパスできるかどうかを制御する
- [-AutoAdmittedロビー](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) をバイパスできるユーザーを制御するユーザー

## <a name="related-topics"></a>関連項目

[Teams アカウントを使用せずに会議に参加する](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Microsoft Teams 管理センターを使用して組織全体のポリシーを構成する](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部参加者は"Teams にサインインして参加するか、会議の開催者に連絡する" を受け取ります](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)