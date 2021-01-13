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
description: '概要: このトピックでは、Skype for Business Server でダイヤルイン会議を構成する方法について説明します。'
ms.openlocfilehash: 92c282c87576e3d46353dabd8235521fe0097c11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820727"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でのダイヤルイン会議の構成
 
**概要:** このトピックでは、Skype for Business Server でダイヤルイン会議を構成する方法について説明します。
  
会議ワークロードと選択したダイヤルイン会議を含むトポロジを作成したら、追加の手順を実行してダイヤルイン会議を構成する必要があります。 このトピックを読む前に [、「Plan for dial-in conferencing in Skype for Business Server,Hardware](../../plan-your-deployment/conferencing/dial-in-conferencing.md) [and software requirements for conferencing in Skype for Business Server,](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。
  
- [ダイヤル プランを構成する](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [ダイヤルイン会議の地域を構成する](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [ダイヤルイン アクセス番号を構成する](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [会議ポリシーを構成する](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [回線 URI をユーザー アカウントに割り当てる](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
また、次のオプション タスクを実行することもできます。 これらのオプション タスクの詳細については、「Skype for Business Server でのダイヤルイン会議の管理」 [を参照してください](../../manage/conferencing/dial-in-conferencing.md)。
  
- ダイヤルイン会議の PIN ポリシーを管理する
    
- DTMF コマンドのキー マッピングを管理する
    
- 会議ディレクトリを作成する
    
- 電話会議の入退出のアナウンスを管理する
    
- ダイヤルイン会議の設定をテストする
    
- ダイヤルイン ユーザーにようこそメールを送信する
    
## <a name="configure-dial-plans"></a>ダイヤル プランを構成する
<a name="BKMK_ConfigureDialPlans"> </a>

ダイヤルイン会議を展開するときは、ダイヤルインのアクセス電話番号をルーティングするために、1 つ以上のダイヤル プランを作成または変更する必要があります。 また、各ダイヤル プランに少なくとも 1 つの正規化ルール (内線電話番号を E.164 形式の完全な電話番号に変換するルール) が含まれる必要があります。 
  
ダイヤルイン会議のユーザーは、自分の暗証番号 (PIN) と電話番号を入力して、認証済みのエンタープライズ ユーザーとして会議に参加します。 内線番号を完全な電話番号に変換する正規化ルールが必要なのは、内線番号だけの入力でユーザーを認証できるようにするためです。
  
ダイヤルイン会議のダイヤル プランを設定するには:
  
- エンタープライズ VoIP を展開するかどうかに関係ない場合は、グローバル ダイヤル プランを変更してダイヤルイン会議の地域を追加し、正規化ルールによってダイヤルイン アクセス番号が正確に変換されます。 詳細な手順については、「Skype for Business Server でダイヤル プランを作成または変更する [」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- ダイヤルイン 会議アクセス番号エンタープライズ VoIP展開しなかった場合は、ダイヤルイン会議アクセス番号のダイヤル プランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細な手順については、「Skype for Business Server でダイヤル プランを作成または変更する [」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- 展開したエンタープライズ VoIP、必要に応エンタープライズ VoIPダイヤル プランを変更して地域を含め、ダイヤルイン アクセス番号に適切な正規化ルールを使用します。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細な手順については、「Skype for Business Server でダイヤル プランを作成または変更する [」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
正規化ルールの作成の詳細については、「Skype for Business での正規化ルールの作成または変更」 [を参照してください](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>ダイヤルイン会議の地域を構成する
<a name="BKMK_ConfigureDialInRegions"> </a>

ダイヤル プランを設定する際に、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。 ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付ける。 ダイヤルイン アクセス番号を作成するときに、アクセス番号を該当するダイヤル プランに関連付ける地域を選択します。 
  
すべてのダイヤル プランの地域を指定することが重要なので、すべてのダイヤル プランに会議の地域が設定されているのを確認することをお勧めします。 
  
地域がすべてのダイヤルイン会議ダイヤル プランに設定されているかどうかを確認するには **、Get-CsDialPlan コマンドレットを使用** します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 Skype for Business Server コントロール パネルを使用して、既存のダイヤル プランの地域を更新することもできます。 Skype for Business Server コントロール パネルの使用の詳細については、「Skype for Business Server でダイヤル プランを作成または変更する [」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1. RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
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
    
詳細については [、「Get-CsDialPlan」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1. RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   次にその例を示します。
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   この例では、Redmond という ID を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 
    
詳細については [、「Set-CsDialPlan」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を構成する
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。
  
ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。 地域の詳細については [、「Plan for dial-in conferencing in Skype for Business Server」を参照してください](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 ダイヤルイン会議のダイヤル プランの構成の詳細については、「Skype for Business Server でダイヤル プランを作成または変更する [」を参照してください](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
> [!NOTE]
> 新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。 レプリケーションが完了するまでに数時間かかることがあります。 
  
> [!NOTE]
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには [、Set-CsDialInConferencingAccessNumber コマンドレットを使用](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) します。 Active Directory のオブジェクトは手動で変更しないでください。
  
### <a name="to-create-a-dial-in-access-number"></a>ダイヤルイン アクセス番号を作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [ **ダイヤルイン アクセス番号] ページ** で、次のいずれかの操作を行います。
    
   - [ **新規] を** クリックして、 **新しいダイヤルイン アクセス番号を開きます**。
    
   - 一覧のダイヤルイン アクセス番号のいずれかをクリックし、[編集]をクリックして、[詳細の表示]**をクリックします**。
    
     > [!NOTE]
     > 検索フィールドを使用してダイヤルイン アクセス番号のリスト内の列の内容を検索すると、期待した結果が得られるとは言えな場合があります。 代わりに、関心のある列で一覧を並べ替え、表示または変更するダイヤルイン アクセス番号を識別します。 
  
5. [ **表示番号]** に、公衆交換電話網 (PSTN) 電話ユーザーが電話会議に参加するためにダイヤルする電話番号を入力します。 この番号は、会議出席依頼とダイヤルイン会議の設定 Web ページに表示されます。
    
6. [ **表示名]** に、ダイヤルイン アクセス番号の説明を入力します。 これは、Skype for Business 検索結果のダイヤルイン アクセス番号に関連付けられている名前です。 この名前は、ユーザーがアクセス番号を呼び出す際にクライアントに表示されます。 
    
7. [ **回線 URI]** で、ダイヤルイン アクセス番号の E.164 番号を TEL URI 形式で入力します。この番号の前に +記号を付け、スペースを除きます。 たとえば、tel:+14255550200 などです。
    
    > [!NOTE]
    > 同じ回線 URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. **SIP URI で、** 次の操作を行います。
    
   - テキスト ボックスに、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI は、通話通知メッセージや以前のバージョンの Lync クライアントなど、さまざまな場所に表示されます。
    
     > [!NOTE]
     > 同じ SIP URI を別のダイヤルイン会議アクセス番号で再利用することはできません。 SIP URI は、アクセス番号の作成後に変更できません。 SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成する方法です。 
  
   - ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議アテンダント アプリケーションのドメインをクリックします。
    
9. [ **プール]** で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行しているプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は [、Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、アクセス番号を削除して再作成する必要があります。
  
10. [ **主言語]** で、このダイヤルイン アクセス番号のプロンプトが再生される言語をクリックします。 
    
    第 1 言語は、会議アテンダントが通話に応答するために使用する言語です。 サポートされている言語は、ダイヤルイン会議の設定 Web ページに各アクセス電話番号と共に表示されます。
    
11. (省略可能)第 **2** 言語 (最大 4つ) で、[追加] をクリックし、このダイヤルイン アクセス番号の発信者に対してサポートする追加の言語を 1 つ以上選択して **、[OK]** をクリックします。 
    
    ダイヤルイン アクセス番号ごとに、最大 4 つの第 2 言語を選択できます。 ユーザーは、会議にダイヤルインするときに会議 ID を入力する前に第 2 言語を選択できます。
    
12. ダイヤルイン アクセス番号の地域を追加するには、[関連付けられた地域] で[追加] をクリックし、このダイヤルイン アクセス番号のダイヤル プランに関連付けられている 1 つ以上の地域をクリックして **、[OK]** をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[関連付けられている地域] で、削除する地域をクリックし、[削除] をクリック **します**。
    
14. [**確定**] をクリックします。
    
## <a name="configure-conferencing-policies"></a>会議ポリシーを構成する
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。 会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。 会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。 複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。 ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。 
  
会議ポリシーの構成の詳細については、「Skype for Business Server での電話会議ポリシーの [管理」を参照してください](../../manage/conferencing/conferencing-policies.md)。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>回線 URI をユーザー アカウントに割り当てる
<a name="BKMK_AssignaLineURI"> </a>

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。 認証には、Skype for Business Server ユーザー アカウントで指定されたテレフォニー回線 **URI** が必要です。
  
このトピックの手順は、**[回線 URI]** を 1 つのユーザー アカウントに対して割り当てる方法について説明します。 **[回線 URI]** を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。 サンプル スクリプトを使用して複数のユーザー アカウントに回線 URI を割り当てる方法の詳細については、「複数のユーザーに回線 **URI** を割り当 [てる」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2.  Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. 検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、**[フィルターの追加]** をクリックして検索フィールドを指定し、次に **[検索]** をクリックします。
    
5. ユーザー名をダブルクリックして **、[Skype for Business Server** ユーザーの編集] ダイアログ ボックスを開きます。
    
6. **[テレフォニー]** の下の **"回線 URI"** フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    > [!NOTE]
    > 回線 **URI** は、テレフォニーが **PC** 間のみ、エンタープライズ VoIP、リモート通話コントロール、またはリモート通話コントロールにのみ設定されている場合にのみ **指定できます**。 
  
7. [**確定**] をクリックします。
    

