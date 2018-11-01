---
title: E9-1-1 ボイス ルートの構成
TOCTitle: E9-1-1 ボイス ルートの構成
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48272389
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# E9-1-1 ボイス ルートの構成

 

_**トピックの最終更新日:** 2012-09-17_

E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。ボイス ルートを作成する方法の詳細については、「[Lync Server 2013 でのボイス ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。


> [!NOTE]
> E9-1-1 INVITE に場所情報を含めるには、緊急通話がゲートウェイを経由してルーティングされるように、E9-1-1 サービス プロバイダーに接続する SIP トランクを構成する必要があります。これを行うには、<strong>Set-CsTrunkConfiguration</strong> コマンドレットの EnablePIDFLOSupport フラグを True に設定します。EnablePIDFLOSupport の既定値は False です。次にその例を示します。<code>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</code><br />
フォールバック公衆交換電話網 (PSTN) ゲートウェイと Emergency Location Identification Number (ELIN) ゲートウェイに対して、場所の受信を有効にする必要はありません。


ボイス ルートの操作の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

## E9-1-1 のボイス ルートを構成するには

1.  RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。
    
    これは、\[場所のポリシー\] の \[**PSTN**\] 設定で使用する名前と同じである必要があります。展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。詳細については、「[Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、\[場所のポリシー\] の\[**緊急ダイヤル文字列**\] 設定で使用する番号パターンと同じである必要があります。Lync で緊急通話に "+" 記号が追加されるように "+" を使用する必要があります。"Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  必要に応じて、SIP トランク接続では、次のコマンドレットを実行することをお勧めします。これにより、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話用のローカル ルートが作成されます。このルートは、E9-1-1サービス プロバイダーに接続できない場合に使用されます。
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

