---
title: Skype for Business Server でダイヤルイン会議を設定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '概要: Skype for Business Server でダイヤルイン会議を構成する方法については、こちらのトピックをお読みください。'
ms.openlocfilehash: ff04637cf077bae4c1408a48a487582a04123b54
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002927"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Skype for Business Server でダイヤルイン会議を設定する
 
**概要:** このトピックでは、Skype for Business Server でダイヤルイン会議を構成する方法について説明します。
  
会議のワークロードと選択されたダイヤルイン会議を含むトポロジを作成した後で、ダイヤルイン会議を構成するための追加の手順を実行する必要があります。 このトピックを読む前に、「Skype for Business server での[ダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)」、「 [Skype for business server の会議のハードウェアとソフトウェアの要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)」、「[ダイヤルイン会議の展開のフローチャートとチェックリスト](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)」を参照してください。 
  
ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
また、以下のオプションのタスクを実行することもできます。 これらのオプションのタスクの詳細については、「 [Skype For Business Server でダイヤルイン会議を管理](../../manage/conferencing/dial-in-conferencing.md)する」を参照してください。
  
- ダイヤルイン会議の PIN ポリシーの管理
    
- DTMF コマンドの主要なマッピングの管理
    
- 電話会議ディレクトリの作成
    
- 電話会議への入退出のアナウンスの管理
    
- ダイヤルイン会議の設定のテスト
    
- ダイヤルイン ユーザーへのようこそメールの送信
    
## <a name="configure-dial-plans"></a>ダイヤル プランを構成する
<a name="BKMK_ConfigureDialPlans"> </a>

ダイヤルイン会議を展開するときに、ダイヤルインアクセス用電話番号をルーティングするための1つ以上のダイヤルプランを作成または変更する必要があります。 また、各ダイヤルプランに少なくとも1つの正規化ルールが含まれていることを確認する必要があります。また、電話の内線番号を完全な電話番号に変更するには、必ず1つのルールを使用してください。 
  
ダイヤルイン会議のユーザーは、自らの暗証番号 (PIN) と電話番号を入力することで、認証されたエンタープライズ ユーザーとして会議に参加します。内線番号を総合的な電話番号に変化する正規化ルールを管理者が定義する必要があり、その結果、ユーザーは内線番号のみを入力したときに認証を受けることができます。
  
ダイヤルイン会議のダイヤル プランをセットアップするには
  
- エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。 詳細な手順については、「 [Skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」を参照してください。
    
- エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議のアクセス電話番号に対応するダイヤル プランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細な手順については、「 [Skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」を参照してください。
    
- エンタープライズ VoIP が展開されている場合は、必要に応じてエンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細な手順については、「 [Skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」を参照してください。
    
正規化ルールの作成の詳細については、「 [Skype For business で正規化ルールを作成または変更](../../deploy/deploy-enterprise-voice/normalization-rules.md)する」を参照してください。
  
## <a name="configure-dial-in-conferencing-regions"></a>ダイヤルイン会議の地域の構成
<a name="BKMK_ConfigureDialInRegions"> </a>

ダイヤル プランをセットアップするときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付けます。ダイヤルイン アクセス番号を作成するときには、アクセス番号と適切なダイヤル プランを関連付ける地域を選択します。 
  
すべてのダイヤル プランに地域を指定することは重要であるため、すべてのダイヤル プランに会議の地域があることを確認するようにお勧めします。 
  
すべてのダイヤルイン会議のダイヤル プランで地域が設定されているかどうかを確認するには、**Get-CsDialPlan** コマンドレットを使用します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 また、Skype for Business Server コントロールパネルを使用して、既存のダイヤルプランの領域を更新することもできます。 Skype for Business Server コントロールパネルの使用について詳しくは、「 [skype For Business server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」をご覧ください。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1. RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   次に例を示します。
    
   ```powershell
   Get-CsDialPlan
   ```

   この例では、組織で構成されているすべてのダイヤル プランが戻されます。
    
4. 戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。 
    
詳細については、「 [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)」を参照してください。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1. RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   この例では、Redmond という Identity を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 
    
詳細については、「 [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)」を参照してください。
  
## <a name="configure-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を構成する
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。
  
ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。 地域の詳細については、「 [Skype For Business Server でのダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)」を参照してください。 ダイヤルイン会議のダイヤルプランの設定の詳細については、「 [Skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」を参照してください。
  
> [!NOTE]
> 新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。レプリケーションが完了するまでに数時間かかることがあります。 
  
> [!NOTE]
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには、 [CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)コマンドレットを使用します。 Active Directory のオブジェクトは手動で変更しないでください。
  
### <a name="to-create-a-dial-in-access-number"></a>ダイヤルイン アクセス番号を作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス番号**] ページで、次のいずれかの操作を行います。
    
   - [**新規**] をクリックして、[**新規ダイヤルイン アクセス番号**] を開きます。
    
   - リストでダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
     > [!NOTE]
     > 検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。 
  
5. [**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。
    
6. [**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。 これは、Skype for Business の検索結果のダイヤルインアクセス番号と関連付けられた名前です。 この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。 
    
7. [**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。
    
    > [!NOTE]
    > 同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. [**SIP URI**] で、次の操作を行ってください。
    
   - テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI は、通話通知メッセージや以前のバージョンの Lync クライアントのように、さまざまな場所に表示されます。
    
     > [!NOTE]
     > 同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。 
  
   - ドロップダウンリストボックスで、ダイヤルインアクセス番号をサポートする会議アテンダントアプリケーションのドメインをクリックします。
    
9. [**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は、[Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。
  
10. [**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。 
    
    第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。
    
11. (オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。 
    
    ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。
    
12. ダイヤルインアクセス番号の領域を追加するには、[**関連付けられた地域**] の [**追加**] をクリックし、このダイヤルインアクセス番号のダイヤルプランに関連付けられている1つ以上の領域をクリックして、[ **OK]** をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。
    
14. [**確定**] をクリックします。
    
## <a name="configure-conferencing-policies"></a>会議ポリシーの構成
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。 
  
会議ポリシーの構成の詳細については、「 [Skype For Business Server の会議ポリシーを管理](../../manage/conferencing/conferencing-policies.md)する」を参照してください。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>ユーザー アカウントに回線 URI を割り当てる
<a name="BKMK_AssignaLineURI"> </a>

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。 Skype for Business Server のユーザーアカウントで指定されたテレフォニー**回線 URI**は、認証に必要です。
  
このトピックの手順は、[**回線 URI**] を 1 つのユーザー アカウントに対して割り当てる方法について説明します。 [**回線 URI**] を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。 複数のユーザーアカウントに**行の uri**を割り当てるサンプルスクリプトの使用について詳しくは、「[複数のユーザーに行](https://go.microsoft.com/fwlink/p/?linkId=196945)の uri を割り当てる」をご覧ください。
  
1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2.  Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. 検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、[**フィルターの追加**] をクリックして検索フィールドを指定し、次に [**検索**] をクリックします。
    
5. ユーザーの名前をダブルクリックして、[**Skype for Business Server ユーザーの編集**] ダイアログ ボックスを開きます。
    
6. [**テレフォニー**] の下の [**回線 URI**] フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    > [!NOTE]
    > [**回線 URI**] を指定できるのは、[**テレフォニー**] が [**PC 間のみ**]、[**エンタープライズ VoIP**]、[**リモート通話コントロール**]、または [**リモート通話コントロールのみ**] に設定されている場合のみです。 
  
7. [**確定**] をクリックします。
    

