---
title: Skype のビジネス サーバーのダイヤルイン会議を構成します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '概要: は、Skype のビジネス サーバーのダイヤルイン会議を構成する方法については、このトピックを読みます。'
ms.openlocfilehash: dbd851f416fb3bc91a556753ce33d2ef80976ff2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226024"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Skype のビジネス サーバーのダイヤルイン会議を構成します。
 
**の概要:** Skype のビジネス サーバーのダイヤルイン会議を構成する方法の詳細については、このトピックを参照してください。
  
会議ワークロードおよびダイヤルイン会議の選択を含むトポロジを作成した後は、ダイヤルイン会議を構成する追加の手順を行う必要があります。 確認すること、このトピックを読む前に読んだ[ビジネス サーバーの Skype では、ダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[ビジネス サーバーの Skype での会議のためのハードウェアおよびソフトウェア要件](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)、および[展開フローチャートとチェックリストダイヤルイン会議](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。 
  
ダイヤルイン会議を構成するには、次のタスクを実行する必要があります。
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
また、以下のオプションのタスクを実行することもできます。 これらの省略可能なタスクの詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の管理](../../manage/conferencing/dial-in-conferencing.md)を参照してください。
  
- ダイヤルイン会議の PIN ポリシーの管理
    
- DTMF コマンドの主要なマッピングの管理
    
- 電話会議ディレクトリの作成
    
- 電話会議への入退出のアナウンスの管理
    
- ダイヤルイン会議の設定のテスト
    
- ダイヤルイン ユーザーへのようこそメールの送信
    
## <a name="configure-dial-plans"></a>ダイヤル プランを構成する
<a name="BKMK_ConfigureDialPlans"> </a>

ダイヤルイン会議を展開するときは、作成またはルーティングのダイヤルインのアクセス電話番号を 1 つまたは複数のダイヤル プランを変更する必要があります。 ダイヤル プランごとに少なくとも 1 つの正規化規則--E.164 形式の完全な電話番号に電話の拡張機能を変換するルールが含まれていることも確認する必要があります。 
  
ダイヤルイン会議のユーザーは、自らの暗証番号 (PIN) と電話番号を入力することで、認証されたエンタープライズ ユーザーとして会議に参加します。内線番号を総合的な電話番号に変化する正規化ルールを管理者が定義する必要があり、その結果、ユーザーは内線番号のみを入力したときに認証を受けることができます。
  
ダイヤルイン会議のダイヤル プランをセットアップするには
  
- エンタープライズ VoIP を展開するかどうかに関係なく、グローバル ダイヤル プランを変更して、ダイヤルイン会議の地域を追加し、正規化ルールによりダイヤルイン アクセス番号が正確に変換されることを確認します。 詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
    
- エンタープライズ VoIP が展開されていない場合は、ダイヤルイン会議のアクセス電話番号に対応するダイヤル プランを作成します。 ダイヤルイン会議の地域を忘れないようにしてください。 詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
    
- エンタープライズ VoIP が展開されている場合は、必要に応じてエンタープライズ VoIP を変更して地域を含め、ダイヤルイン アクセス番号のための適切な正規化ルールを使用します。 また、ダイヤルイン アクセス番号のみのために使用する、専用のダイヤル プランを作成することもできます。 詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
    
正規化ルールを作成する方法についてを参照してください[を作成するまたはビジネス用の Skype の正規化ルールを変更する](../../deploy/deploy-enterprise-voice/normalization-rules.md)です。
  
## <a name="configure-dial-in-conferencing-regions"></a>ダイヤルイン会議の地域の構成
<a name="BKMK_ConfigureDialInRegions"> </a>

ダイヤル プランをセットアップするときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を適切なダイヤル プランに関連付けます。ダイヤルイン アクセス番号を作成するときには、アクセス番号と適切なダイヤル プランを関連付ける地域を選択します。 
  
すべてのダイヤル プランに地域を指定することは重要であるため、すべてのダイヤル プランに会議の地域があることを確認するようにお勧めします。 
  
すべてのダイヤルイン会議のダイヤル プランで地域が設定されているかどうかを確認するには、**Get-CsDialPlan** コマンドレットを使用します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 既存のダイヤル プラン内の領域を更新するのには Skype ビジネス サーバーのコントロール パネルを使用することもできます。 Skype のビジネス サーバーのコントロール パネルの使用に関する詳細についてを参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1. RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   次に例を示します。
    
   ```
   Get-CsDialPlan
   ```

   この例では、組織で構成されているすべてのダイヤル プランが戻されます。
    
4. 戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。 
    
詳細については、 [Get CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)を参照してください。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1. RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例:
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   この例では、Redmond という Identity を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 
    
詳細については、[一連の CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)を参照してください。
  
## <a name="configure-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を構成する
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と [ダイヤルイン会議の設定] Web ページに表示されます。
  
ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。 領域に関する詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の計画](../../plan-your-deployment/conferencing/dial-in-conferencing.md)を参照してください。 ダイヤルイン会議の計画をダイヤルすると、構成の詳細について参照してください[を作成するまたはビジネス サーバーの Skype のダイヤル プランを変更する](../../deploy/deploy-enterprise-voice/dial-plans.md)です。
  
> [!NOTE]
> 新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。レプリケーションが完了するまでに数時間かかることがあります。 
  
> [!NOTE]
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには、[セット CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)コマンドレットを使用します。 Active Directory のオブジェクトは手動で変更しないでください。
  
### <a name="to-create-a-dial-in-access-number"></a>ダイヤルイン アクセス番号を作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**会議**] をクリックし、[**ダイヤルイン アクセス番号**] をクリックします。
    
4. [**ダイヤルイン アクセス番号**] ページで、次のいずれかの操作を行います。
    
   - [**新規**] をクリックして、[**新規ダイヤルイン アクセス番号**] を開きます。
    
   - リストでダイヤルイン アクセス番号のいずれかをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
     > [!NOTE]
     > 検索フィールドを使用してダイヤルイン アクセス番号のリストの列の内容を検索しても、結果が予想どおりにならない場合があります。代わりに、対象の列を基にしてリストを並べ替えて、表示または変更するダイヤルイン アクセス番号を特定してください。 
  
5. [**表示番号**] に、公衆交換電話網 (PSTN) 電話を使用するユーザーが会議に参加するときにダイヤルする、電話番号を入力します。この番号は、会議出席依頼とダイヤルイン会議設定 Web ページに表示されます。
    
6. [**表示名**] に、ダイヤルイン アクセス番号の説明を入力します。 これは、ビジネスの検索結果の Skype でダイヤルイン アクセス番号に関連付けられている名前です。 この名前は、ユーザーがアクセス番号を呼び出すとき、クライアントで表示されます。 
    
7. [**回線 URI**] に、ダイヤルイン アクセス番号の E.164 番号を、電話番号の前に + 記号を付加し、スペースを含めない電話 URI 形式で入力します。たとえば、tel:+14255550200 のように入力します。
    
    > [!NOTE]
    > 同じ回線 URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。 
  
8. [**SIP URI**] で、次の操作を行ってください。
    
   - テキスト ボックスで、このダイヤルイン会議アクセス番号の一意の SIP URI を入力します。 この SIP URI などのさまざまな場所が通知メッセージ、および以前のバージョンの Lync クライアントの呼び出しに限定されません。
    
     > [!NOTE]
     > 同じ SIP URI を、別のダイヤルイン会議アクセス番号で再利用することはできません。SIP URI を、アクセス番号の作成後に変更することはできません。SIP URI を変更する唯一の方法は、アクセス番号を削除して再作成することです。 
  
   - ドロップダウン リスト ボックスで、このダイヤルイン アクセス番号をサポートする会議アテンダント アプリケーションのドメインをクリックします。
    
9. [**プール**] で、このダイヤルイン アクセス番号をサポートする会議アテンダントのインスタンスを実行するプールをクリックします。
    
    > [!NOTE]
    > アクセス番号の作成後にプールを変更する必要がある場合は、[Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) コマンドレットを使用するか、またはアクセス番号をいったん削除して作成し直す必要があります。
  
10. [**第 1 言語**] で、このダイヤルイン アクセス番号の案内を再生するときに使用される言語をクリックします。 
    
    第 1 言語とは、会議アテンダントが着信への応答に使用する言語のことです。サポートされている言語は、各アクセス電話番号と共に、ダイヤルイン会議の設定 Web ページに表示されます。
    
11. (オプション) [**第 2 言語 (4 つまで)**] で、[**追加**] をクリックして、このダイヤルイン アクセス番号への発信者用にサポートする 1 つ以上の追加言語を選択し、[**OK**] をクリックします。 
    
    ダイヤルイン アクセス番号ごとに最大 4 つの第 2 言語を選択できます。ユーザーは、会議にダイヤルインする際に会議 ID を入力する前に、第 2 言語を選択できます。
    
12. ダイヤルイン アクセス番号、**関連付けられた領域**の下の領域を追加するには、[**追加**] をクリックして、このダイヤルイン アクセス番号をダイヤル プランに関連付けられ、 **[ok]** をクリックし、1 つまたは複数の領域をクリックします。
    
13. ダイヤルイン アクセス番号から地域を削除するには、[**関連付けられている地域**] で削除する地域をクリックし、[**削除**] をクリックします。
    
14. [**確定**] をクリックします。
    
## <a name="configure-conferencing-policies"></a>会議ポリシーの構成
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会議ポリシーは、参加者向けの会議機能を指定するユーザー アカウント設定です。会議ポリシーは、サイト スコープまたはユーザー スコープで作成できます。会議ポリシー設定には、会議の予約と参加の多くの側面が含まれます。複数の会議ポリシー設定で、参加者向けのダイヤルイン会議をサポートしています。ダイヤルイン会議を構成する際に、これらのフィールドが組織に適切に設定されていることを確認し、必要に応じて変更する必要があります。 
  
会議ポリシーを構成する方法の詳細については、 [Skype ビジネス サーバーの会議ポリシーの管理](../../manage/conferencing/conferencing-policies.md)を参照してください。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>ユーザー アカウントに回線 URI を割り当てる
<a name="BKMK_AssignaLineURI"> </a>

ダイヤルイン ユーザーは各自の電話番号または内線番号、それに PIN を入力し、認証されたユーザーとして会議に参加します。 テレフォニー ビジネス サーバーのユーザー アカウントの Skype で指定された**行の URI**は、認証に必要です。
  
このトピックの手順は、[**回線 URI**] を 1 つのユーザー アカウントに対して割り当てる方法について説明します。 [**回線 URI**] を複数のユーザー アカウントに対して割り当てる必要がある場合は、**Set-CsUser** コマンドレットを使用するスクリプトを作成できます。 **回線 URI**を複数のユーザー アカウントに割り当てるには、サンプル スクリプトの使用に関する詳細については、[複数のユーザーに回線 Uri を割り当てる](https://go.microsoft.com/fwlink/p/?linkId=196945)を参照してください。
  
1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**Cs-UserAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。
    
2.  Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. 検索フィールドで、ダイヤルイン会議の構成を行うユーザーの名前を入力するか、[**フィルターの追加**] をクリックして検索フィールドを指定し、次に [**検索**] をクリックします。
    
5. ユーザーの名前をダブルクリックして、[**Skype for Business Server ユーザーの編集**] ダイアログ ボックスを開きます。
    
6. [**テレフォニー**] の下の [**回線 URI**] フィールドで、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
    > [!NOTE]
    > [**回線 URI**] を指定できるのは、[**テレフォニー**] が [**PC 間のみ**]、[**エンタープライズ VoIP**]、[**リモート通話コントロール**]、または [**リモート通話コントロールのみ**] に設定されている場合のみです。 
  
7. [**確定**] をクリックします。
    

