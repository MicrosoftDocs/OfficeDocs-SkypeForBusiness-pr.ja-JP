---
title: 'Lync Server 2013: 1-1 のボイスルーティングを構成する E9'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d40d2ee5dcb0dd7f759751bdab0d3e09f4ebc577
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Lync Server 2013 での E9 音声ルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 ボイスルートの作成の詳細については、「 [Lync Server 2013 での音声ルートの作成](lync-server-2013-create-a-voice-route.md)」を参照してください。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。

<div>


> [!NOTE]  
> E9 の招待状に位置情報を含めるには、E9 サービスプロバイダーに接続する SIP トランクをゲートウェイ経由でルーティングするように構成する必要があります。 そのためには、 <STRONG>set-cstrunkconfiguration</STRONG>コマンドレットの EnablePIDFLOSupport フラグを True に設定します。 EnablePIDFLOSupport の既定値は False です。 例えば：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>フォールバック公衆交換電話網 (PSTN) ゲートウェイと Emergency Location Identification Number (ELIN) ゲートウェイに対して、場所の受信を有効にする必要はありません。



</div>

ボイスルートの使用について詳しくは、次のコマンドレットの Lync Server 管理シェルに関するドキュメントをご覧ください。

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **新規-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1.  RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については、「[ボイスポリシーと PSTN 使用状況レコードを構成する」を参照してください。 Lync Server 2013 で通話機能と特権を承認](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)します。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 Lync は緊急通話に "+" を追加するため、"+" 記号が必要です。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  必要に応じて、SIP トランク接続では、次のコマンドレットを実行することをお勧めします。これにより、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話用のローカル ルートが作成されます。このルートは、E9-1-1サービス プロバイダーに接続できない場合に使用されます。
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

