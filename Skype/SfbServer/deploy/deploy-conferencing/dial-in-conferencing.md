---
title: Skype for Business Server でのダイヤルイン会議の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '概要: Skype for Business Server でダイヤルイン会議を構成する方法については、このトピックを参照してください。'
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103853"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でのダイヤルイン会議の構成
 
**概要:** Skype for Business Server でダイヤルイン会議を構成する方法については、このトピックを参照してください。
  
会議ワークロードと選択されたダイヤルイン会議を含むトポロジを作成したら、ダイヤルイン会議を構成するための追加の手順を実行する必要があります。 このトピックを読む前に[、「Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md)でのダイヤルイン会議の計画」、Skype for Business [Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)での会議のハードウェアとソフトウェアの要件[](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)、およびダイヤルイン会議の展開フローチャートとチェックリストを参照してください。 
  
ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。
  
- [ダイヤル プランを構成する](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [ダイヤルイン会議地域の構成](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [ダイヤルイン アクセス番号を構成する](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [会議ポリシーの構成](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [ユーザー アカウントに回線 URI を割り当てる](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
さらに、次のオプション タスクを実行することもできます。 これらのオプション タスクの詳細については [、「Manage dial-in conferencing in Skype for Business Server」を参照してください](../../manage/conferencing/dial-in-conferencing.md)。
  
- ダイヤルイン会議の PIN ポリシーを管理する
    
- DTMF コマンドのキー マッピングを管理する
    
- 会議ディレクトリの作成
    
- 会議への参加と退会のお知らせを管理する
    
- ダイヤルイン会議の設定をテストする
    
- ダイヤルイン ユーザーにウェルカム メールを送信する
    
## <a name="configure-dial-plans"></a>ダイヤル プランを構成する
<a name="BKMK_ConfigureDialPlans"> </a>

ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。 また、各ダイヤル プランに少なくとも 1 つの正規化ルール (内線番号を E.164 形式の完全な電話番号に変換するルール) が含まれている必要があります。 
  
ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。 内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。
  
ダイヤルイン会議のダイヤル プランを設定するには、次の方法を実行します。
  
- エンタープライズ VoIP を展開するかどうかに関係ない場合は、グローバル ダイヤル プランを変更してダイヤルイン会議地域を追加し、正規化ルールによってダイヤルイン アクセス番号が正確に変換されるかどうかを確認します。 詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- ダイヤルイン会議のアクセスエンタープライズ VoIP展開しなかった場合は、ダイヤルイン会議アクセス番号のダイヤル プランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- このサービスを展開エンタープライズ VoIP、必要にエンタープライズ VoIP必要に応じてダイヤル プランを変更し、ダイヤルイン アクセス番号に適切な正規化ルールを使用します。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細な手順については、「Create or modify a [dial plan in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
正規化ルールの作成の詳細については、「Skype for Business で正規化ルールを [作成または変更する」を参照してください](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>ダイヤルイン会議地域の構成
<a name="BKMK_ConfigureDialInRegions"> </a>

ダイヤル プランを設定する際に、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。 ダイヤルイン会議地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付ける。 ダイヤルイン アクセス番号を作成するときに、アクセス番号を該当するダイヤル プランに関連付ける地域を選択します。 
  
すべてのダイヤル プランに地域を指定することが重要なので、すべてのダイヤル プランに電話会議地域が設定されているのを確認することをお勧めします。 
  
すべてのダイヤルイン会議ダイヤル プランに地域が設定されているかどうかを確認するには **、Get-CsDialPlan コマンドレットを使用** します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 Skype for Business Server コントロール パネルを使用して、既存のダイヤル プランの地域を更新することもできます。 Skype for Business Server コントロール パネルの使用の詳細については、「Create or modify a dial plan [in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1. RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   次にその例を示します。
    
   ```powershell
   Get-CsDialPlan
   ```

   この例では、組織で構成されているすべてのダイヤル プランが戻されます。
    
4. 戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。 
    
詳細については [、「Get-CsDialPlan」を参照してください](/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1. RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   次にその例を示します。
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   この例では、Redmond という ID を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 
    
詳細については [、「Set-CsDialPlan」を参照してください](/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を構成する
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。
  
ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。 地域の詳細については [、「Plan for dial-in conferencing in Skype for Business Server」を参照してください](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 ダイヤルイン会議のダイヤル プランの構成の詳細については、「Create or modify a dial plan [in Skype for Business Server」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
> [!NOTE]
> 新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。 レプリケーションが完了するまでに数時間かかることがあります。 
  
> [!NOTE]
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには [、Set-CsDialInConferencingAccessNumber コマンドレットを使用](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) します。 Active Directory のオブジェクトは手動で変更しないでください。
  
### <a name="to-create-a-dial-in-access-number"></a>ダイヤルイン アクセス番号を作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [ダイヤル **イン アクセス番号] ページで** 、次のいずれかの操作を行います。
    
   - [ **新規] を** クリックして[ **新しいダイヤルイン アクセス番号] を開きます**。
    
   - 一覧でダイヤルイン アクセス番号のいずれかをクリックし、[編集]をクリックし、[詳細の表示]**をクリックします**。
    
     > [!NOTE]
     > 検索フィールドを使用して、ダイヤルイン アクセス番号の一覧にある列の内容を検索すると、期待した結果が得られるとは思いません。 代わりに、リストを関心のある列で並べ替え、表示または変更するダイヤルイン アクセス番号を識別します。 
  
5. [ **表示番号]** に、公衆交換電話網 (PSTN) 電話ユーザーが電話会議に参加するためにダイヤルする電話番号を入力します。 この番号は、会議出席依頼とダイヤルイン会議の設定 Web ページに表示されます。
    
6. [ **表示名]** に、ダイヤルイン アクセス番号の説明を入力します。 これは、Skype for Business 検索結果のダイヤルイン アクセス番号に関連付けられている名前です。 この名前は、ユーザーがアクセス番号を呼び出す際にクライアントに表示されます。 
    
7. [ **行 URI]** に、ダイヤルイン アクセス番号の E.164 番号を TEL URI 形式で入力します。この番号の前に + 記号を付け、スペースを除きます。 たとえば、tel:+14255550200。
    
    > [!NOTE]
    > 同じ回線 URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. **SIP URI で、** 次の操作を行います。
    
   - テキスト ボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI は、呼び出し通知メッセージや以前のバージョンの Lync クライアントなど、さまざまな場所に表示されます。ただし、これらに限定されません。
    
     > [!NOTE]
     > 同じ SIP URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 SIP URI は、アクセス番号の作成後に変更できません。 SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成する方法です。 
  
   - ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議応答アプリケーションのドメインをクリックします。
    
9. [ **プール]** で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は [、Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、アクセス番号を削除して再作成する必要があります。
  
10. [ **プライマリ言語]** で、このダイヤルイン アクセス番号のプロンプトを再生する言語をクリックします。 
    
    プライマリ言語は、会議アテンダントが通話に応答するために使用する言語です。 サポートされている言語は、[ダイヤルイン会議の設定] Web ページの各アクセス電話番号と一緒に表示されます。
    
11. (省略可能)[セカンダリ言語 (最大 **4 言語)]** で、[追加] をクリックし、このダイヤルイン アクセス番号の発信者をサポートする 1 つ以上の追加言語を選択し **、[OK]** をクリックします。  
    
    ダイヤルイン アクセス番号ごとに最大 4 つのセカンダリ言語を選択できます。 ユーザーは、会議にダイヤルインするときに会議 ID を入力する前に、第 2 言語を選択できます。
    
12. ダイヤルイン アクセス番号の地域を追加するには、[関連付けられた地域] で、[追加] をクリックし、このダイヤルイン アクセス番号のダイヤル プランに関連付けられている 1 つ以上の地域をクリックし **、[OK]** をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[関連付けられた地域] で、削除する地域をクリックし、[削除] をクリック **します**。
    
14. [**確定**] をクリックします。
    
## <a name="configure-conferencing-policies"></a>会議ポリシーの構成
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。 会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。 会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。 複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。 ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。 
  
会議ポリシーの構成の詳細については、「Skype for Business Server での会議ポリシーの管理 [」を参照してください](../../manage/conferencing/conferencing-policies.md)。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>ユーザー アカウントに回線 URI を割り当てる
<a name="BKMK_AssignaLineURI"> </a>

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。 認証 **には、Skype** for Business Server ユーザー アカウントで指定されたテレフォニー回線 URI が必要です。
  
このトピックの手順は、**[回線 URI]** を 1 つのユーザー アカウントに対して割り当てる方法について説明します。 **[回線 URI]** を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。 サンプル スクリプトを使用して複数のユーザー アカウントに **回線 URI** を割り当てる方法の詳細については、「複数のユーザーに回線 URI を割り当てる」 [を参照してください](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. 検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、**[フィルターの追加]** をクリックして検索フィールドを指定し、次に **[検索]** をクリックします。
    
5. ユーザー名をダブルクリックして **、[Skype for Business Server ユーザーの編集] ダイアログ ボックスを** 開きます。
    
6. **[テレフォニー]** の下の **"回線 URI"** フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    > [!NOTE]
    > 回線 **URI** を指定できるのは、**テレ** フォニーが **PC** 間のみ、エンタープライズ VoIP、リモート通話制御、またはリモート通話 **制御のみに設定されている場合のみです**。  
  
7. [**確定**] をクリックします。
