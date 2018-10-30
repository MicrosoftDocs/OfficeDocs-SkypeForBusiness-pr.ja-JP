---
title: Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの割り当て
TOCTitle: Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの割り当て
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48273737
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの割り当て

 

_**トピックの最終更新日:** 2010-11-07_

ユーザー単位のホスト ボイス メール ポリシーを展開するかどうかはオプションです。 ユーザー単位のポリシーを展開する場合は、ユーザー、グループ、または連絡先オブジェクトにポリシーを明示的に割り当てる必要があります。

ユーザー単位のホスト ボイス メール ポリシーの割り当て、または割り当ての削除の詳細については、Lync Server 管理シェル のドキュメントにある以下のコマンドレットの説明を参照してください。

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## ユーザー単位のホスト ボイス メール ポリシーを割り当てるには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Grant-CsHostedVoicemailPolicy コマンドレットを実行して、個々のユーザー、グループ、および連絡先オブジェクトにユーザー単位のホスト ボイス メール ポリシーを割り当てます。たとえば、以下を実行します。
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    この例では、ExRedmond ホスト ボイス メール ポリシーを Ken Myer に割り当てました。
    
    **Identity** により、変更するユーザー アカウントを指定しています。 Identity 値は、以下の形式のいずれかで指定できます。
    
      - ユーザーの SIP アドレス
    
      - ユーザーの Active Directory ユーザー プリンシパル名
    
      - ユーザーのドメイン\\ログオン名 (例: contoso\\kenmyer)
    
      - ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。 表示名を Identity 値として使用する場合は、アスタリスク (\*) ワイルドカード文字を使用できます。 たとえば、"\* Smith" という Identity は、末尾が " Smith" という文字列値の表示名を持つすべてのユーザーを戻します。
    
    > [!NOTE]
    > ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。

