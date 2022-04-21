---
title: 電話会議の無料電話番号ポリシー
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: Microsoft 365またはOffice 365での電話会議で、ユーザーが自分の携帯電話から会議を呼び出す方法について説明します。
ms.openlocfilehash: 11e1e493db38b5e830b3334f659d23f86b6b56ba
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65017001"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>有料電話番号とフリーダイヤル番号の電話会議ポリシー設定

## <a name="teams-audio-conferencing-policy"></a>電話会議ポリシーをTeamsする

電話会議ポリシーを使用して、組織内のユーザーが作成した会議出席依頼に表示される電話会議の有料電話番号とフリーダイヤル番号を管理します。 自動的に作成された 2 つのポリシーのいずれかを使用するか、カスタム ポリシーを作成して割り当てることができます。 自動的に作成される 2 つのポリシーは、グローバル (組織全体の既定値) と AllowTollFreeDialinFalse (フリー ダイヤルイン番号が有効になっていない組織内のすべての既存のユーザーに割り当てられます) です。 電話会議ポリシーは、Microsoft Teams管理センターまたは [PowerShell](teams-powershell-overview.md) を使用して管理します。

- AllowTollFreeDialin の設定は、Teams管理センターまたは PowerShell を使用して個々のユーザーに対して管理できなくなりました。 テナント管理者は、新しい電話会議ポリシーを使用してのみこの設定を管理できます。
- グローバル ポリシーは、Teams管理センターから変更することはできません。

テナントでTeams電話会議ポリシーを有効にすると、テナントで自動的に作成される 2 つのポリシーが使用可能になります。 自動的に作成された 2 つのポリシーとその既定の設定は次のとおりです。

### <a name="global-org-wide-default"></a>グローバル (組織全体の既定値)

このポリシーでは **、AllowTollfreedialin** の値が ON に設定され、ポリシーに電話番号が定義されることはありません。 これは、起動時に **AllowTollfreedialin** が **[オン**] に設定されているテナント内のすべてのユーザーの既定のポリシーです。
ポリシーには電話番号が定義されていないため、このポリシーのユーザーがTeams会議を作成すると、会議で使用できる電話番号は、ポリシーの前にユーザーが持っていたのと同じ電話番号になります。 これらの電話番号は、通常、個々のユーザーのテナント管理者によって変更されない限り、ユーザーの国/場所に既定で設定されます。

たとえば、ドイツを拠点とするユーザーに、電話会議ポリシーの開始前にドイツの有料電話番号とフリーダイヤル電話番号が割り当てられていた場合、起動時にユーザーにグローバル ポリシーが割り当てられ、会議への招待で引き続き表示される電話番号はポリシーが適用される前と同じになります (つまり、 ドイツの有料電話番号とフリーダイヤル番号)。 ポリシーの起動時に、エンド ユーザーに変更は表示されません。 ただし、テナント管理者がグローバル ポリシーを変更し、以前とは異なる特定の電話番号をポリシーに含める場合、ポリシーのすべてのユーザーには、スケジュールした会議にポリシーに含まれる電話番号のみが表示されます。

> [!NOTE]
> グローバル ポリシーを変更する代わりに、テナント管理者がカスタム ポリシーを作成してユーザーに適用する場合、カスタム ポリシーで定義されている設定は、エンド ユーザーが会議の招待に表示する内容になります。

たとえば、カスタム ポリシーに "AllowTollFreeDialinFalse" があり、電話番号が定義されていない場合、このポリシーのユーザーは無料電話番号を持つことができません。また、ポリシーに電話番号が定義されていないため、そのようなユーザーが作成した会議出席依頼で使用される有料電話番号は、ポリシーの前にユーザーが持っていたのと同じ電話番号になります。 これらの電話番号は、通常、個々のユーザーのテナント管理者によって変更されない限り、ユーザーの国/場所に既定で設定されます。

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

このポリシーでは **、AllowTollfreedialin** の値が **[オフ]** に設定され、ポリシーに電話番号が定義されることはありません。 これは、起動時に **AllowTollfreedialin** を **[オフ**] に設定したテナント内のすべてのユーザーの既定のポリシーです。

ポリシーには電話番号が定義されていないため、このポリシーのユーザーがチーム会議を作成すると、会議で使用できる電話番号は、ポリシーの前にユーザーが持っていたのと同じ電話番号になります。 通常、これらの電話番号は、個々のユーザーのテナント管理者によって変更されていない限り、ユーザーの国、地域、または場所に既定で設定されます。

たとえば、ドイツを拠点とするユーザーが電話会議ポリシーの開始前にドイツの有料電話番号を割り当てていた場合、起動時にユーザーに "AllowTollfreedialinFalse" ポリシーが割り当てられ、会議への招待で引き続き表示される電話番号は以前と同じになります (つまり、ドイツの有料電話番号)。 ポリシーの起動時に、エンド ユーザーに変更は表示されません。 ただし、テナント管理者が **AllowTollfreedialinFalse** ポリシーを変更し、特定の電話番号をポリシーに含める場合、すべてのポリシー ユーザーに表示されるのは、スケジュールした会議にポリシーに含まれる電話番号のみです。

## <a name="create-a-custom-audio-conferencing-policy"></a>カスタム電話会議ポリシーを作成する

手順の概要:

1. Microsoft Teams管理センターの左側のナビゲーションで、会議>電話会議に移動します。
1. [追加] を選択します。
1. ポリシーの名前と説明を入力します。 名前に特殊文字を含めたり、64 文字より長くすることはできません。
1. 希望する設定を選びます。
1. [保存] を選択します。

たとえば、複数の国の参加者と定期的に会議を行うユーザーのグループがあるとします。 この例では、参加者はカナダ、ボツワナ、シンガポールのユーザーであり、全員が電話番号をダイヤルして電話会議を通じて会議に参加したいと考えています。 "Canada ボツワナ シンガポール" という名前の新しいカスタム ポリシーを作成し、[電話番号の **追加]** オプションを使用してポリシーに含めるこれら 3 つの国の電話番号を選択し、このポリシーを保存できます。 その後、このポリシーを必要なユーザーに割り当てることができます。

これにより、カナダ、ボツワナ、シンガポールで選択した電話番号が、このポリシーのユーザーによって作成された会議への招待に含まれます。

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>例に基づいてカスタム ポリシーを作成する手順

1. Microsoft Teams管理センターの左側のナビゲーションで、**MeetingsAudio** >  会議に移動 **します**。
2. **[追加]** を選択します。
3. ポリシーの名前と説明を入力します。 名前に特殊文字を含めたり、64 文字より長くすることはできません。
4. このポリシーのユーザーによって作成された会議にフリーダイヤル番号を含めるかどうかを選択します。 これを **[オン]** に設定すると、このポリシーにフリーダイヤル電話番号を追加できます。
5. [電話番号の追加] を選択します。
6. 画面の右側にウィンドウが開き、[ **場所別の検索** ] ボックスが表示されます。
7. カナダを入力し、結果からカナダの電話番号を選択します。
8. **[追加]** を選択します。
9. 手順 6 と 7 を同じ方法で繰り返して、ボツワナとシンガポールから電話番号を検索して追加します。
10. [手順 4. **でこのポリシーのユーザーが作成した会議にフリーダイヤル番号を含める** ] の設定をオンにしている場合は、フリーダイヤル番号を選択します。
11. ウィンドウの右下隅にある [ **追加]** を選択します。 選択した 3 つの国の電話番号が一覧表示されます。
12. このポリシーのユーザーが作成した会議への招待に電話番号を表示する順序を決定するランク列があります。 電話番号を選択し、[上へ移動] ボタンと [**下** へ移動] ボタンを使用して上下に **移動** することで、順序を変更できます。
13. 電話番号を好みの順序で入力したら、[ **保存]** を選択します。
14. "Canada ボツワナ シンガポール" という名前のカスタム ポリシーが作成されます。
15. 作成が完了したら、このポリシーをユーザーに割り当てることができます。

## <a name="edit-a-meeting-policy"></a>会議 ポリシーの編集

作成した任意のカスタム ポリシーを編集できます。 (グローバル ポリシーはTeams管理センターから編集できないことに注意してください)

1. Microsoft Teams管理センターの左側のナビゲーションで、**MeetingsAudio** >  会議に移動 **します**。
1. 編集するポリシーを選択するには、ポリシー名の左側を選択し、[ **編集]** を選択します。
1. 編集を行います。
1. **[保存]** を選択します。

> [!NOTE]
> ユーザーが割り当てられているポリシーは削除できません。 影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があります。その後、元のポリシーを削除できます。

## <a name="assign-a-meeting-policy-to-users"></a>ユーザーに会議ポリシーを割り当てる

> [!IMPORTANT]
> 新しい電話会議ポリシーがユーザーに適用されると、ポリシーで定義されている電話番号は、このポリシーを使用してユーザーが作成した新しい会議でのみ使用できます。 ポリシーの前にスケジュールされた古い会議と定期的な会議は、古い設定 (1 つの有料電話番号と 1 つのフリーダイヤル番号など) を引き続き表示します (そのユーザーに対して無料通話が有効になっている場合)。 ここでは、ユーザーが **フリーダイヤルを許可** し、フリーダイヤル番号を割り当て、今後定期的な会議を作成した可能性があります。 このシナリオでは、AllowTollfreeDialIn を **オフ** にしてこのユーザーに適用するカスタム ポリシーを作成した場合、このユーザーによって作成された新しい会議にはフリーダイヤル番号は含まれませんが、古い定期的な会議にはフリーダイヤル番号が表示されます。 そのため、呼び出し元がこのフリーダイヤル番号をダイヤルして会議に参加すると、通話は失敗します。これは、ポリシーが原因で、このユーザーのフリーダイヤルが無効になっているためです。 これを防ぐために、新しい電話会議ポリシーを割り当てた後、ユーザーの古い会議を移行できます。 [会議移行サービス (MMS) の使用](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)を確認してください。

ユーザーまたはユーザーが属するグループに直接ポリシーを割り当てることができます (ポリシーの種類がサポートされている場合)、バッチ割り当て (ポリシーの種類でサポートされている場合) を通じて、個別に、またはより大きな数値でポリシーを割り当てることができます。

ユーザーにポリシーを割り当てることができるさまざまな方法については、「ユーザー [とグループにポリシーを割り当てる](assign-policies-users-and-groups.md)」を参照してください。

> [!NOTE]
> ユーザーに割り当てることができる電話会議ポリシーは、一度に 1 つだけです。

### <a name="known-issue"></a>既知の問題

[カレンダー] > [Meet Mow] の Microsoft Teams > [**今すぐ会議**] オプションを使用して会議を開始する場合は、省略記号 [...] を選択します。メニュー オプション、会議情報の順に選択すると、[**Or call in (オーディオのみ)]** セクションの下部に問題が発生します。 ポリシーで定義されているすべての電話番号が表示されますが、番号の配置により読み取りが困難になります。