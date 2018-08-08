---
title: ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '概要: は、Skype のビジネス サーバーのエンタープライズ VoIP を使用して呼び出しを受信しユーザーを有効にする方法を説明します。'
ms.openlocfilehash: abba652665660299ccb1e3b9a55961ca2248225e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025667"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。
 
**の概要:** 行うし、Skype のビジネス サーバーのエンタープライズ VoIP を使用して呼び出しを受信するユーザーを有効にする方法を説明します。
  
エンタープライズ VoIP または作業時間を使用して呼び出しを配置した後は、エンタープライズ VoIP を使用して呼び出しを行うユーザーを有効にするのには次の手順を使用できます。
  
> [!NOTE]
> 次の手順では、ビジネス サーバーのコントロール パネルの Skype を使用して、最初のものだけを実行できます。 残りの手順では、ビジネスのサーバー管理シェルの Skype のみを使用できます。 
  
- エンタープライズ VoIP のユーザー アカウントを有効にします。
    
- (オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。
    
- (オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>エンタープライズ VoIP のユーザー アカウントを有効にするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. テーブルでは、エンタープライズ VoIP を有効にするユーザー アカウントをクリックします。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. **ビジネス サーバー ユーザーの Skype の編集**] ページで、[**テレフォニー**]、[**エンタープライズ VoIP**をクリックします。
    
8. [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。
    
9. [**確定**] をクリックします。
    
エンタープライズ VoIP に対してユーザーを有効にするを終了するには必ず音声ポリシーとダイヤル プランにユーザーが割り当てられているグローバルかどうか (既定では割り当てられている) か、ユーザー固有です。既定では、すべてのユーザーは、グローバル音声ポリシーが割り当てられているし、ダイヤル プランです。 ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。 ユーザーごとの音声ポリシーを適用またはダイヤル プランのユーザーには、**補助金 CsVoicePolicy**と**与える CsDialPlan**コマンドレットを実行してください。 詳細については、このトピックの以下の手順を参照してください。
## <a name="voice-policy-assignment"></a>音声ポリシーの割り当て

グローバルおよびサイト レベルの音声ポリシーは、エンタープライズ VoIP を有効になっているすべてのユーザー アカウントに自動的に割り当てられます。 特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。 このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。 グローバルを使用して、またはエンタープライズ VoIP を有効にするすべてのユーザーの音声ポリシーをサイトにする場合は、このセクションをスキップし、このトピックの後半の[ダイヤル プランの割り当て](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)」を続行できます。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>ユーザー固有の音声ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例:
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    この例では、Bob 友野の表示名を持つユーザーには**VoicePolicyJapan**という名前の音声ポリシーが割り当てられます。
    
## <a name="dial-plan-assignment"></a>ダイヤル プランの割り当て
<a name="BKMK_DialPlanAssignment"> </a>

ユーザーのエンタープライズ VoIP またはダイヤルイン会議のユーザーのユーザー アカウントの構成を完了するためにユーザー割り当てる必要がありますダイヤル プランです。 既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。 使用して、グローバルまたはサイトのエンタープライズ VoIP を有効にするすべてのユーザーのダイヤル プランにする場合は、このセクションを省略できます。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>ユーザー固有のダイヤル プランを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例:
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    この例では、Bob 友野の表示名を持つユーザーには**DialPlanJapan**という名前のユーザーのダイヤル プランが割り当てられます。
    

