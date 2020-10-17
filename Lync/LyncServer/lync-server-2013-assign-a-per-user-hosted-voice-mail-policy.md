---
title: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの割り当て'
description: 'Lync Server 2013: ユーザーごとのホストボイスメールポリシーの割り当て。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559893"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる

 


ユーザー単位のホスト ボイス メール ポリシーを展開するかどうかはオプションです。 ユーザー単位のポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトにポリシーを明示的に割り当てる必要があります。

ユーザー単位のホストボイスメールポリシーの割り当てまたは削除の詳細については、以下のコマンドレットの Lync Server Management Shell のドキュメントを参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>ユーザー単位のホスト ボイス メール ポリシーを割り当てるには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Grant-CsHostedVoicemailPolicy コマンドレットを実行して、個々のユーザー、グループ、および連絡先オブジェクトにユーザー単位のホスト ボイス メール ポリシーを割り当てます。たとえば、以下を実行します。
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    この例では、ExRedmond ホスト ボイス メール ポリシーを Ken Myer に割り当てました。
    
    **Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。
    
      - ユーザーの SIP アドレス
    
      - ユーザーの Active Directory ユーザー プリンシパル名
    
      - ユーザーのドメイン \\ ログオン名 (たとえば、contoso \\ kenmyer)
    
      - ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。 Display-Name を Identity 値として使用する場合は、アスタリスク ( \* ) ワイルドカード文字を使用できます。 たとえば、"smith" という Id は、" \* smith" という文字列値で終わる Display-Name を持つすべてのユーザーを返します。
    

    > [!NOTE]  
    > ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。


