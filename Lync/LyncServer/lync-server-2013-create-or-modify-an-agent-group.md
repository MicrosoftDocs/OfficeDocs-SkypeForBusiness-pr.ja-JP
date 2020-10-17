---
title: 'Lync Server 2013: エージェントグループを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 874b73af42869bc5cbe6a66b7efaf792d231b95d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525754"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Lync Server 2013 でエージェントグループを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。

<div>


> [!NOTE]  
> CsVoiceAdministrator などの管理者は、ユーザーがエージェントグループに割り当てられる前に、エンタープライズ Voip および Lync Server に対してユーザーを有効にする必要があります。 管理ワークフローの委任された応答グループ マネージャーであれば、エージェント グループを作成し、管理するワークフローでそのグループを使用できます。



</div>

<div>


> [!IMPORTANT]  
> ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを通知してください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Lync Server コントロールパネルを使用してエージェントグループを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    <div>
    

    > [!NOTE]  
    > 管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。

    
    </div>

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。

4.  [**グループ**] ページで、次のいずれかの操作を行います。
    
      - 新規エージェント グループを作成するには、[**新規**] をクリックします。[**サービスの選択**] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前のすべてまたは一部を入力します。サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。
    
      - 既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前のすべてまたは一部を入力します。結果一覧で、対象のグループをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。

5.  [**名前**] に、エージェント グループの識別名を入力します。

6.  [**説明**] に、グループの説明を入力します。

7.  [**参加ポリシー**] で、以下のいずれかを選択してグループのサインイン動作を設定します。
    
      - グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、[**非公式**] を選択します。 エージェントは、Lync Server 2013 にサインインすると自動的にグループにサインインします。
    
      - グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、[**公式**] を選択します。 このオプションを選択すると、エージェントは Lync のメニュー項目をクリックして、Internet Explorer を開き、グループにサインインまたはサインアウトするための web ページコンソールを表示します。

8.  [**警告時間 (秒)**] で、次の有効なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。

    
    </div>

9.  [**ルーティング方法**] で、グループのエージェントに通話をルーティングする方法を次のように指定します。
    
      - 新しい通話を最初にアイドル状態になった (Lync Server で **利用可能** な状態または **非アクティブ** な状態になっていた) エージェントに最初に提供するには、[ **最長アイドル**] をクリックします。
    
      - 新しい通話を、有効なすべてのエージェントに同時に提供するには、[**パラレル**] をクリックします。 通話は、最初に受け付けたエージェントに送られます。
    
      - 新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] をクリックします。
    
      - 新しい通話を、常に [**エージェント**] リストでのリスト順でエージェントに提供するには、[**シリアル**] をクリックします。
    
      - 現在のプレゼンスに関係なく、Lync Server 2013 および応答グループアプリケーションにサインインしているすべてのエージェントに対して同時に新しい通話を提供するには、[ **アテンダント**] をクリックします。 Lync 2010 アテンダントユーザーがエージェントとして構成されている場合は、待機中のすべての通話、および任意の順序で待機通話に応答することができます。 呼び出しは、それを受け入れる最初のエージェントに送信され、その後、他の Lync 2010 アテンダントユーザーが通話を表示しなくなります。

10. [**エージェント**] で、エージェント リストの作成方法を指定します。
    
      - エージェントのカスタム リストを使用するには、[**エージェントのカスタム グループを定義する**] をクリックして、次のいずれかの操作を行います。
        
          - ユーザーをエージェント グループに追加するには、[**選択**] をクリックして [**エージェントの選択**] 検索フィールドで、このグループに追加するユーザーの名前または名前の一部を入力して [**検索**] をクリックします。エージェントの結果リストで、ユーザーをクリックして [**OK**] をクリックします。
        
          - エージェント グループからユーザーを削除するには、エージェントのリストで削除するユーザーをクリックし [**削除**] をクリックします。
        
          - ラウンド ロビン ルーティングまたはシリアル ルーティングのいずれかを使用するグループでエージェントが通話を提供される順序を変更するには、エージェントのリストで、ユーザーをクリックして上矢印または下矢印をクリックします。
    
      - Microsoft Exchange Server 配布リストをエージェント グループとして使用するには、[**既存の電子メール配布リストを使用する**] をクリックし、[**配布リストのアドレス**] に配布リストの電子メール アドレス (NetworkSupport@contoso.com など) を入力します。
        
        電子メール配布リストを使用する場合には、次の制約があります。
        
          - エージェント グループに対して複数の配布リストを選択することはできません。 各グループでサポートされる配布リストは 1 つのみです。
        
          - 配布リストの中に別の配布リストが含まれている場合、入れ子となった配布リストのメンバーはエージェント リストに追加されません。
        
          - シリアルまたはラウンド ロビン ルーティングを選択した場合、着信通話はサーバーによってルーティング方法および配布リスト内のエージェントの順序に基づいて適切なエージェントに提供されます。
        
          - 配布リストに Lync Server 2010 が有効になっているが、エンタープライズ Voip が有効になっていないユーザーが含まれている場合、それらのユーザーは中エージェントとしてエージェントグループに追加されます。 配布リストのすべてのメンバーのユーザーアカウントに対してエンタープライズ Voip が有効になっていることを確認します。
        
        <div>
        

        > [!IMPORTANT]  
        > 電子メール配布リストを使用する場合、非表示のメンバーシップまたは非表示のリストが応答グループの管理者またはユーザーに表示されることがあります。

        
        </div>
        
        非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。
        
          - メンバーシップが非表示になるように配布リストが構成されており、応答グループの管理者が配布リストをエージェントリストに割り当てると、ユーザーはグループを呼び出して、メンバーが誰であるかを確認できます。
        
          - 配布リストが Exchange グローバルアドレス一覧で非表示になるように構成されている場合、応答グループの管理者が適切なユーザー権限とアクセス許可を持っていない場合でも、応答グループプロセスに適切なユーザー権限とアクセス許可がある場合は、配布リストを表示してエージェントリストに割り当てることができます。

11. [**確定**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Windows PowerShell を使用してエージェントグループを作成または変更するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  新規エージェント グループを作成するには、**New-CsRgsAgentGroup** を使用します。 既存のエージェント グループを変更するには、**Set-CsRgsAgentGroup** を使用します。 コマンド ラインで、次のコマンドを実行します。
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    次に例を示します。
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。

    
    </div>

4.  次のコマンドを実行して、エージェント グループが作成されたことを確認します。
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でエージェントグループを削除する](lync-server-2013-delete-an-agent-group.md)  


[Lync Server 2013 での応答グループエージェントグループの管理](lync-server-2013-managing-response-group-agent-groups.md)  
[取得-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

