---
title: 'Lync Server 2013: エンタープライズ Voip のユーザーを有効にする'
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
ms.openlocfilehash: 0b851c8807e12456c600b2ca176b0fa5a834f0d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

1つ以上の仲介サーバーのファイルをインストールして、発信通話ルーティングを構成し、必要に応じて1つ以上の高度なエンタープライズ音声機能を展開するには、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにします。

<div>


> [!NOTE]  
> 次の手順では、最初の操作は Lync Server コントロールパネルを使用して行うことができます。 残りの手順については、Lync Server 管理シェルのみを使用できます。



</div>

  - エンタープライズ Voip のユーザーアカウントを有効にします。

  - (オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。

  - (オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを有効にするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。

5.  表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**詳細の表示**] をクリックします。

7.  [ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] をクリックします。

8.  [**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。

9.  [**確定**] をクリックします。

エンタープライズ Voip のユーザーを有効にするには、そのユーザーに、グローバル (既定で割り当てられている) か、またはユーザー固有かにかかわらず、ボイスポリシーとダイヤルプランが割り当てられていることを確認します。

既定では、すべてのユーザーにグローバル音声ポリシーとダイヤル プランが割り当てられます。 ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。 ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。 詳細については、「 [Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)のドキュメント」を参照してください。

</div>

<div>

## <a name="voice-policy-assignment"></a>音声ポリシーの割り当て

グローバルおよびサイトレベルのボイスポリシーは、エンタープライズ Voip が有効になっているすべてのユーザーアカウントに自動的に割り当てられます。 特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。 このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。 エンタープライズ Voip を有効にしているすべてのユーザーに対して、グローバルまたはサイトのボイスポリシーを使用する場合は、このセクションをスキップして、このトピックの後半の「プランの割り当てを続行する」セクションを参照してください。

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>ユーザー固有の音声ポリシーを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    次に例を示します。
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    この例では、表示名が Bob 友野のユーザーに、 **VoicePolicyJapan**という名前のボイスポリシーが割り当てられています。

ユーザー固有の音声ポリシーを割り当てる方法、または**Grant-CsVoicePolicy**コマンドレットを実行する方法の詳細については、「 [Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)のドキュメント」を参照してください。

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>ダイヤル プランの割り当て

ダイヤルイン会議のエンタープライズボイスまたはユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。 既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。 エンタープライズ Voip を有効にしているすべてのユーザーに対してグローバルまたはサイトダイヤルプランを使用する場合は、このセクションをスキップできます。

<div>

## <a name="to-assign-a-dial-plan"></a>ダイヤルプランを割り当てるには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    例:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    この例では、"Bob 友野" という名前のユーザーにダイヤルプランが割り当てられ**ています。**

ユーザーダイヤルプランの割り当てまたは**Grant-CsDialPlan**コマンドレットの実行について詳しくは、「 [Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)のドキュメント」をご覧ください。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でエンタープライズ Voip のユーザーを無効にする](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

