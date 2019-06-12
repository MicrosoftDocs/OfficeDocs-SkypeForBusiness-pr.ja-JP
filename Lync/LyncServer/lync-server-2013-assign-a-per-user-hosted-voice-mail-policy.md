---
title: 'Lync Server 2013: ユーザーごとにホストされるボイスメールポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848844"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる

 


ユーザーごとにホストされるボイスメールのポリシーを1つ以上展開することは任意です。 ユーザーごとのポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。

ユーザーごとにホストされるボイスメールポリシーの割り当てまたは削除の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>ユーザーごとにホストされるボイスメールのポリシーを割り当てるには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  CsHostedVoicemailPolicy コマンドレットを実行して、ユーザーごとにホストされるボイスメールポリシーを個々のユーザー、グループ、連絡先オブジェクトに割り当てます。 たとえば、以下を実行します。
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    この例では、ユーザー Ken Myer に ExRedmond でホストされるボイスメールポリシーを割り当てました。
    
    **Id**は、変更するユーザーアカウントを指定します。 Id 値は、次の形式のいずれかを使用して指定できます。
    
      - ユーザーの SIP アドレス
    
      - ユーザーの Active Directory ユーザープリンシパル名
    
      - ユーザーのドメイン\\ログオン名 (たとえば、contoso\\kenmyer)
    
      - ユーザーの Active Directory ドメインサービスの表示名 (Ken Myer など) Id 値として表示名を使用している場合は、アスタリスク (\*) ワイルドカード文字を使うことができます。 たとえば、"\* smith" という id を指定すると、"smith" という文字列で終わる表示名を持つすべてのユーザーが返されます。
    

    > [!NOTE]  
    > SAM アカウント名はフォレスト内で必ずしも一意ではないため、ユーザーの Active Directory SAM アカウント名を Id 値として使用することはできません。


