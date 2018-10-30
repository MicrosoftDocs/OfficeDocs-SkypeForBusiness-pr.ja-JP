---
title: 'Lync Server 2013: ホスト型ボイス メールに対するユーザーの有効化'
TOCTitle: ホスト型ボイス メールに対するユーザーの有効化
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48274184
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのホスト型ボイス メールに対するユーザーの有効化

 

_**トピックの最終更新日:** 2012-09-24_

手順に従い、Hosted Exchange ユニファイド メッセージング (UM) サービスで、 Lync Server 2013 ユーザーをボイス メールに対して有効にします。

詳細は、「計画」のドキュメントの「[Lync Server 2013 の Hosted Exchange ユーザー管理](lync-server-2013-hosted-exchange-user-management.md)」を参照してください。

[Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser) コマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。


> [!IMPORTANT]
> Lync Server 2013 のユーザーがホスト ボイス メールを使用できるようにするには、そのユーザー アカウントに適用されるホスト ボイス メール ポリシーをまず展開する必要があります。詳細については、「<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 のホスト型ボイス メール ポリシー</A>」を参照してください。



## ホスト ボイス メールに対してユーザーを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsUser コマンドレットを実行して、ホスト ボイス メールに対応するようにユーザー アカウントを構成します。たとえば、以下を実行します。
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    上述の例では、次のパラメーターが設定されます。
    
      - **HostedVoiceMail** は、ユーザーのボイス メール通話を Hosted Exchange UM にルーティングできるようにします。また、これによって Microsoft Lync 2013 の "ボイス メールの呼び出し" インジケーターが点灯します。
    
      - **Identity** により、変更するユーザー アカウントを指定しています。Identity 値は、以下の形式のいずれかで指定できます。
        
          - ユーザーの SIP アドレス
        
          - ユーザーの Active Directory ユーザー プリンシパル名
        
          - ユーザーのドメイン\\ログオン名 (例: contoso\\kenmyer)
        
          - ユーザーの Active Directory ドメイン サービス表示名 (例: Ken Myer)。表示名を Identity 値として使用する場合は、アスタリスク (\*) ワイルドカード文字を使用できます。たとえば、"\* Smith" という Identity は、末尾が " Smith" という文字列値の表示名を持つすべてのユーザーを戻します。
        
        > [!NOTE]  
        > ユーザーの Active Directory SAM アカウント名は、フォレスト内で一意の名前とは限らないため、Identity 値として使用することはできません。

