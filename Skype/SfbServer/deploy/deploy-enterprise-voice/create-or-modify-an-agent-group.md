---
title: Skype for Business でエージェント グループを作成または変更する
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Skype for Business Server の応答グループで、エージェント グループを作成または変更エンタープライズ VoIP。
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837097"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Skype for Business でエージェント グループを作成または変更する
 
Skype for Business Server の応答グループで、エージェント グループを作成または変更エンタープライズ VoIP。
  
エージェント グループを作成するときに、グループに割り当てられているエージェントを選択し、ルーティング方法、エージェントがグループにサインインおよびサインアウトできるかどうかなどの追加のグループ設定を指定します。 
  
Skype for Business のサインインまたはサインアウトとは異なる、グループにサインインおよびサインアウトする必要があるエージェントを、公式エージェントと呼ぶ。 正式なエージェントは、グループにルーティングされた通話を受信する前に、グループにサインインする必要があります。 これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。 公式エージェントは、Skype for Business のメニュー項目をクリックして Windows Internet Explorer インターネット ブラウザーを開き、Web ページ コンソールを表示することで、グループにサインインおよびサインアウトします。
  
グループにサインインまたはサインアウトしないエージェントを非公式エージェントと呼ぶ。 非公式エージェントは、Skype for Business にサインインすると自動的にグループにサインインし、グループからサインアウトすることはできません。
  
社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。
  
エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。
  
> [!IMPORTANT]
> ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを通知してください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Skype for Business Server コントロール パネルを使用してエージェント グループを作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    > [!NOTE]
    > 管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。 
  
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。
    
4. [**グループ**] ページで、次のいずれかの操作を行います。
    
   - 新規エージェント グループを作成するには、[**新規**] をクリックします。[**サービスの選択**] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前のすべてまたは一部を入力します。サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。
    
   - 既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前のすべてまたは一部を入力します。結果一覧で、対象のグループをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。
    
5. [**名前**] に、エージェント グループの識別名を入力します。
    
6. [**説明**] に、グループの説明を入力します。
    
7. [**参加ポリシー**] で、以下のいずれかを選択してグループのサインイン動作を設定します。
    
   - グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、[**非公式**] を選択します。 エージェントは、Skype for Business にサインインすると自動的にグループにサインインします。
    
   - グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、[**公式**] を選択します。 このオプションを選択すると、エージェントは Skype for Business のメニュー項目をクリックして Internet Explorer を開き、グループにサインイン/サインアウトする Web ページ コンソールを表示します。
    
8. [**警告時間 (秒)**] で、次の有効なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。
    
    > [!IMPORTANT]
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。 
  
9. [**ルーティング方法**] で、グループのエージェントに通話をルーティングする方法を次のように指定します。
    
   - 最も長いアイドル状態 (Skype for Business で利用可能または非アクティブな状態が最も長い) エージェントに最初に新しい呼び出しを提供するには、[最長アイドル] をクリック **します**。 
    
   - 新しい通話を、有効なすべてのエージェントに同時に提供するには、[**パラレル**] をクリックします。 通話は、最初に受け付けたエージェントに送られます。
    
   - 新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] をクリックします。 
    
   - 新しい通話を、常に [**エージェント**] リストでのリスト順でエージェントに提供するには、[**シリアル**] をクリックします。 
    
   - Skype for Business と応答グループ アプリケーションに同時にサインインしているすべてのエージェントに新しい通話を提供するには、現在のプレゼンスに関係なく **、[Attendant]** をクリックします。 エージェントとして構成されているユーザーは、待機中のすべての通話を任意の順序で表示し、待機中の通話に応答できます。 通話は、最初に受け付けしたエージェントに送信され、その後、他のエージェントには通話が表示されません。
    
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
    
      - 配布リストに Lync Server 2010 が有効になっているが、エンタープライズ VoIP が有効になっていないユーザーが含まれている場合、そのユーザーはエージェント グループに異常なエージェントとして追加されます。 配布リストのすべてのメンバーがユーザー アカウントに対してエンタープライズ VoIP有効にしてください。
    
    > [!IMPORTANT]
    > 電子メール配布リストを使用すると、非表示のメンバーシップまたは非表示のリストが応答グループ管理者またはユーザーに表示される可能性があります。 
  
    非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。
    
     - メンバーシップが非表示にするように配布リストが構成され、応答グループ管理者が配布リストをエージェント リストに割り当てると、ユーザーはグループを呼び出してメンバーを確認できます。 
    
     - Exchange グローバル アドレス一覧で非表示にするように配布リストが構成されている場合、応答グループの管理者が適切なユーザー権限とアクセス許可を持っていなくても、応答グループのプロセスに適切なユーザー権限とアクセス許可がある場合、応答グループ管理者は配布リストを表示してエージェント リストに割り当て可能な場合があります。
    
11. [**確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Skype for Business Server 管理シェルを使用してエージェント グループを作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. 新規エージェント グループを作成するには、**New-CsRgsAgentGroup** を使用します。 既存のエージェント グループを変更するには、**Set-CsRgsAgentGroup** を使用します。 コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    次に例を示します。
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。 
  
4. 次のコマンドを実行して、エージェント グループが作成されたことを確認します。
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>関連項目

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
