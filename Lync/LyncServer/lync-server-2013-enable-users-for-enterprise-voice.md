---
title: 'Lync Server 2013: エンタープライズ Voip でユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31b9cffef7dbb9338c1019b965fb398a0f72ed34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

1つ以上の仲介サーバーのファイルをインストールした後、発信通話ルーティングを構成し、オプションで1つ以上の高度なエンタープライズ Voip 機能を展開するには、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにします。

<div>


> [!NOTE]  
> 次の手順では、最初の操作は Lync Server コントロールパネルを使用して実行することができます。 その他の手順については、「Lync Server Management Shell」のみを使用できます。



</div>

  - エンタープライズ Voip のユーザーアカウントを有効にします。

  - (オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。

  - (オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5.  表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] をクリックします。

8.  [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。

9.  [**確定**] をクリックします。

エンタープライズ Voip に対してユーザーを有効にするには、ユーザーに音声ポリシーとダイヤルプランが割り当てられているかどうか (既定で割り当てられているか、ユーザー固有であるか) を確認します。

既定では、すべてのユーザーにグローバル音声ポリシーとダイヤル プランが割り当てられます。 ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。 ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。 詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。

</div>

<div>

## <a name="voice-policy-assignment"></a>音声ポリシーの割り当て

エンタープライズ Voip が有効になっているすべてのユーザーアカウントに、グローバルおよびサイトレベルの音声ポリシーが自動的に割り当てられます。 特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。 このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。 エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトの音声ポリシーを使用する場合は、このセクションをスキップして、このトピックで後述する「ダイヤルプランの割り当て」セクションを続行することができます。

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>ユーザー固有の音声ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    次に例を示します。
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    この例では、表示名が Bob 友野のユーザーには、 **voicepolicyjapan という**という名前の音声ポリシーが割り当てられます。

ユーザー固有の音声ポリシーの割り当て、または**set-csvoicepolicy**コマンドレットの実行の詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>ダイヤル プランの割り当て

エンタープライズ Voip またはダイヤルイン会議のユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。 既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。 エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションを省略できます。

<div>

## <a name="to-assign-a-dial-plan"></a>ダイヤル プランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    次にその例を示します。
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    この例では、表示名が Bob 友野のユーザーには、ダイヤルプラン**日本**という名前のユーザーダイヤルプランが割り当てられます。

ユーザーダイヤルプランの割り当て、または**get-csdialplan**コマンドレットの実行に関する詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

