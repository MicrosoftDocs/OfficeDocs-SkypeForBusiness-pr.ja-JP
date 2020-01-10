---
title: Skype for Business でキューを作成または変更する
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
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Skype for Business Server Enterprise Voice で応答グループキューを作成または変更します。
ms.openlocfilehash: 9027c239c92c7c04b9de8b5579d7ebb73069b1a3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001707"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Skype for Business でキューを作成または変更する
 
Skype for Business Server Enterprise Voice で応答グループキューを作成または変更します。
  
エージェントが通話に応答するまで、キューには発信者が保持されます。 応答グループアプリケーションは、利用可能なエージェントを検索するときに、一覧に表示されている順序でエージェントグループを検索します。 キューに割り当てられるエージェント グループを選択し、キューに保持する通話の最大数や、エージェントが応答するまで通話を待機させる時間などのキューの動作を指定できます。
  
キューを作成または変更するには、以下のいずれかの手順を使用します。
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Skype for Business Server コントロールパネルを使用してキューを作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    > [!NOTE]
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、応答グループ キューを作成または変更して、管理するワークグループに割り当てることができます。 
  
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**応答グループ**] をクリックし、[**キュー**] をクリックします。
    
4. [**キュー**] ページで、次のいずれかの操作を実行します。
    
   - 新しいキューを作成するには、[**新規作成**] をクリックします。 [**サービスの選択**] の検索フィールドに、キューを追加する **ApplicationServer** サービスの名前の一部またはすべてを入力します。 表示されたサービスの一覧で、目的のサービスをクリックし、[**OK**] をクリックします。
    
   - 既存のキューを変更するには、キューの名前または名前の一部を検索フィールドに入力します。結果のキューの一覧で、対象のキューをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
5. [**名前**] にキューの識別名を入力します。
    
6. [**説明**] に、キューの説明を入力します。
    
7. [**グループ**] で、キューに割り当てるグループを指定します。次のいずれかの操作を行います。 
    
   - キューにグループを追加するには、[**選択**] をクリックします。[**グループの選択**] の検索フィールドに、キューに割り当てるエージェント グループの名前または名前の一部を入力し、一覧で目的のエージェント グループをクリックして、[**OK**] をクリックします。
    
   - キューからグループを削除するには、エージェント グループの一覧で、削除するグループをクリックし、[**削除**] をクリックします。
    
   - エージェントを検索する順序を変更するには、エージェント グループの一覧でグループをクリックし、上矢印または下矢印をクリックします。
    
     > [!NOTE]
     > サーバーでは、キューで利用可能なエージェントを検索するときには、グループの順序が使用されます。つまり、一覧の最初のグループが最初に検索され、一覧の 2 番目のグループが次に検索され、以降も同様に検索されます。 
  
8. エージェントが通話に応答するまで発信者を保留状態にする最長時間を指定するには、[**キューのタイムアウトを有効にする**] チェック ボックスをオンにして次の操作を実行します。
    
    a. [**タイムアウト時間 (秒)**] で、エージェントが通話に応答するのを発信者が待つ最大秒数を指定します。
    
    b. [**通話アクション**] で、呼び出しがタイムアウトになったときに行う動作を次のように選択します。
    
   - タイムアウト後通話を終了するには、[**切断**] をクリックします。
    
   - 通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**] フィールドに、「sip: * \<\>username*@ *\<domainname\> * (sip:bob@contoso.com)」という形式でボイスメールアドレスを入力します。
    
   - 別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックし、[ **sip アドレス**] フィールドに電話番号を「sip: * \<\>番号*@ *\<の\>ドメイン名*」という形式で入力します (たとえば、sip:+14255550121@contoso.com)。
    
   - 通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip _ \<:\>username_@ _\<domainname\>_」という形式で入力します。
    
   - 別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。
    
9. キューに保持できる最大通話数を指定するには、[**キューのオーバーフローを有効にする**] チェック ボックスをオンにして次の操作を実行します。
    
    a. [**最大通話数**] で、キューで保持する最大通話数を選択します。 
    
    b. [**通話の転送**] で、キューが一杯になったときに転送する通話を、[**最新の通話**] または [**最も古い通話**] から選択します。
    
    c. [**通話アクション**] で、オーバーフローしきい値に達したときに実行する処理を、次のように選択します。
    
   - タイムアウト後通話を終了するには、[**切断**] をクリックします。
    
   - 通話をボイスメールに転送するには、[**ボイスメールに転送**] をクリックし、[ **sip アドレス**] フィールドに、「sip: * \<\>username*@ *\<domainname\> * (sip:bob@contoso.com)」という形式でボイスメールアドレスを入力します。
    
   - 別の電話番号に通話を転送するには、[**電話番号に転送**] をクリックし、[ **sip アドレス**] フィールドに電話番号を「sip: * \<\>番号*@ *\<の\>ドメイン名*」という形式で入力します (たとえば、sip:+14255550121@contoso.com)。
    
   - 通話を別のユーザーに転送するには、[ **sip アドレスに転送**] をクリックし、[ **sip アドレス**] フィールドにユーザーの URI を「sip _ \<:\>username_@ _\<domainname\>_」という形式で入力します。
    
   - 別のキューに通話を転送する場合は [**別のキューに転送**] をクリックし、使用するキューを参照します。
    
10. [**確定**] をクリックします。
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Skype for Business Server 管理シェルを使用してキューを作成または変更するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
    > [!NOTE]
    > 管理ワークフローを委任された応答グループ マネージャーのいずれかである場合は、エージェント グループおよびキューを作成して、エージェント グループをキューに割り当てることができます。 
  
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. キューのタイムアウトしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   次に例を示します。
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > プロンプトにオーディオ ファイルを使用するには、 **Import-CsRgsAudioFile** コマンドレットを使用します。 詳細については、「[インポート-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)」を参照してください。 
  
4. キューのタイムアウトしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > 可能なアクションとその構文の詳細については、「[新しい-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)」を参照してください。 
  
    次に例を示します。
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. キューのオーバーフローしきい値に達したときに再生されるプロンプトを作成し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   次に例を示します。
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > プロンプトにオーディオ ファイルを使用するには、 **Import-CsRgsAudioFile** コマンドレットを使用します。 詳細については、「[インポート-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)」を参照してください。 
  
6. キューのオーバーフローしきい値に達したときに実行されるアクションを定義し、変数に格納します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > 可能なアクションとその構文の詳細については、「[新しい-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)」を参照してください。 
  
    次に例を示します。
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. 応答グループ サービスのサービス名を取得し、変数に割り当てます。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. キューに割り当てるエージェント グループの Identity を取得します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > エージェントグループの作成の詳細については、「[新しい-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps) 」を参照してください。
  
9. キューを作成します。コマンド ラインで、次のコマンドを実行します。
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   例:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. キューが作成されたことを確認します。次のコマンドレットを実行します。
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>関連項目

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
