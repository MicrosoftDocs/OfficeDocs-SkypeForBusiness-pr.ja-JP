---
title: 'Lync Server 2013: E9-1-1 ボイスルートの構成'
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
ms.openlocfilehash: e0a14c540ca8d9a8655f215449d90716cf6834f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Lync Server 2013 での E9-1-1 ボイスルートの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-17_

E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 ボイスルートの作成の詳細については、「 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)」を参照してください。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。

<div>


> [!NOTE]  
> E9-1-1 招待に位置情報を含めるには、E9-1-1 サービスプロバイダーに接続する SIP トランクを構成して、ゲートウェイ経由で緊急通話をルーティングする必要があります。 これを行うには、 <STRONG>get-cstrunkconfiguration</STRONG>コマンドレットの EnablePIDFLOSupport フラグを True に設定します。 EnablePIDFLOSupport の既定値は False です。 例えば：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>フォールバック公衆交換電話網 (PSTN) ゲートウェイと Emergency Location Identification Number (ELIN) ゲートウェイに対して、場所の受信を有効にする必要はありません。



</div>

ボイスルートの使用の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1.  RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については、「 [Lync Server 2013 で通話機能および権限を承認するための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の[**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 Lync が緊急電話に "+" を追加するため、"+" 記号が必要になります。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
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

