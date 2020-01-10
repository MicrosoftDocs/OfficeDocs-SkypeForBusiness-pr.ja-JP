---
title: Skype for Business Server でエンタープライズ Voip のユーザーを有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '概要: Skype for Business Server のエンタープライズボイスを使用して、ユーザーが通話を発信および受信できるようにする方法について説明します。'
ms.openlocfilehash: 441b7a5705268dedea1feb87e01a48d0ef68b32c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002527"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Skype for Business Server でエンタープライズ Voip のユーザーを有効にする
 
**概要:** Skype for Business Server のエンタープライズボイスを使用して、ユーザーが通話を発信および受信できるようにする方法について説明します。
  
職場で企業の音声または通話を展開した後、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにすることができます。
  
> [!NOTE]
> 次の手順では、最初の操作は、Skype for Business Server コントロールパネルを使用して行うことができます。 残りの手順については、Skype for Business Server 管理シェルのみを使用できます。 
  
- エンタープライズ Voip のユーザーアカウントを有効にします。
    
- (オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。
    
- (オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを有効にするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. 表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. [ **Skype For Business Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] をクリックします。
    
8. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
9. [**確定**] をクリックします。
    
エンタープライズ Voip のユーザーを有効にするには、そのユーザーに、グローバル (既定で割り当てられている) か、またはユーザー固有かにかかわらず、ボイスポリシーとダイヤルプランが割り当てられていることを確認します。既定では、すべてのユーザーにグローバルボイスポリシーとダイヤルプランが割り当てられています。 ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。 ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。 詳細については、このトピックの以下の手順を参照してください。
## <a name="voice-policy-assignment"></a>音声ポリシーの割り当て

グローバルおよびサイトレベルのボイスポリシーは、エンタープライズ Voip が有効になっているすべてのユーザーアカウントに自動的に割り当てられます。 特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。 このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。 エンタープライズ Voip を有効にしているすべてのユーザーに対して、グローバルまたはサイトのボイスポリシーを使用する場合は、このセクションをスキップして、このトピックの後半の「[プランの割り当て](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)を続行する」セクションを参照してください。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>ユーザー固有の音声ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    次に例を示します。
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    この例では、表示名が Bob 友野のユーザーに、 **VoicePolicyJapan**という名前のボイスポリシーが割り当てられています。
    
## <a name="dial-plan-assignment"></a>ダイヤル プランの割り当て
<a name="BKMK_DialPlanAssignment"> </a>

ダイヤルイン会議のエンタープライズボイスまたはユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。 既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。 エンタープライズ Voip を有効にしているすべてのユーザーに対してグローバルまたはサイトダイヤルプランを使用する場合は、このセクションをスキップできます。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>ユーザー固有のダイヤル プランを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例:
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    この例では、"Bob 友野" という名前のユーザーにダイヤルプランが割り当てられ**ています。**
    

