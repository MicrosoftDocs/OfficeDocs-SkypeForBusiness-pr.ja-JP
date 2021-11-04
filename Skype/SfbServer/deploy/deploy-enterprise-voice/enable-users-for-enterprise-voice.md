---
title: ユーザーがユーザーのエンタープライズ VoIPを有効Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '概要: ユーザーが通話を行い、受信する方法については、ユーザーが エンタープライズ VoIPを使用Skype for Business Server。'
ms.openlocfilehash: 27c60b7532411c50d6613635a28a638a5cfbc97d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749368"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>ユーザーがユーザーのエンタープライズ VoIPを有効Skype for Business Server
 
**概要:** ユーザーが通話を行い、受信する方法については、エンタープライズ VoIPをSkype for Business Server。
  
ユーザーが エンタープライズ VoIPまたは Call Via Work を展開した後、次の手順を使用して、ユーザーが次の手順を使用して通話をエンタープライズ VoIP。
  
> [!NOTE]
> 次の手順の中で、コントロール パネルを使用して最初Skype for Business Server実行できます。 残りの手順では、管理シェルでのみSkype for Business Server使用できます。 
  
- ユーザー アカウントのユーザー アカウントを有効エンタープライズ VoIP。
    
- (オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。
    
- (オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>ユーザー アカウントでユーザー アカウントを有効にするにはエンタープライズ VoIP

1. RTCUniversalServerAdmins グループのメンバーとして、または **CsVoiceAdministrator 、CsServerAdministrator、** または **CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。
    
5. 表で、ユーザー アカウントで有効にするユーザー アカウントをクリックエンタープライズ VoIP。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. [ユーザーの **編集Skype for Business Server] ページ** の [テレフォニー]**で、[** ユーザーの設定]**をエンタープライズ VoIP。**
    
8. [ **回線 URI]** をクリックし、正規化された一意の電話番号 (たとえば) を入力します `tel:+14255550200` 。
    
9. [**確定**] をクリックします。
    
エンタープライズ VoIP のユーザーの有効化を完了するには、グローバル (既定で割り当てられている) またはユーザー固有の音声ポリシーとダイヤル プランがユーザーに割り当てられている必要があります。既定では、すべてのユーザーにグローバル音声ポリシーとダイヤル プランが割り当てられます。 ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。 ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。 詳細については、このトピックの以下の手順を参照してください。
## <a name="voice-policy-assignment"></a>音声ポリシーの割り当て

グローバルおよびサイト レベルの音声ポリシーは、ユーザー アカウントに対して有効になっているすべてのユーザー アカウントに自動的エンタープライズ VoIP。 特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。 このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。 エンタープライズ VoIP で有効になっているすべてのユーザーにグローバルまたはサイト音声ポリシーを使用する場合は、このセクションをスキップして、このトピックの後半の「[](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)ダイヤル プランの割り当て」セクションに進む必要があります。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>ユーザー固有の音声ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    次にその例を示します。
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    この例では、表示名 Bob Kelly を持つユーザーに VoicePolicyJapan という名前の音声ポリシー **が割り当てられます**。
    
## <a name="dial-plan-assignment"></a>ダイヤル プランの割り当て
<a name="BKMK_DialPlanAssignment"> </a>

電話会議のユーザーまたはダイヤルイン会議エンタープライズ VoIPのユーザー アカウント構成を完了するには、ユーザーにダイヤル プランを割り当てる必要があります。 既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。 グローバル ダイヤル プランまたはサイト ダイヤル プランを、ユーザーが有効になっているすべてのユーザーにエンタープライズ VoIP、このセクションをスキップできます。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>ユーザー固有のダイヤル プランを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    次にその例を示します。
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    この例では、表示名 Bob Kelly を持つユーザーに DialPlanJapan という名前のユーザー ダイヤル プラン **が割り当てられます**。
    

