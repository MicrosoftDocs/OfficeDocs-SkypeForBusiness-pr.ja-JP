---
title: Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの作成
TOCTitle: Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの作成
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48271793
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの作成

 

_**トピックの最終更新日:** 2012-09-24_

ユーザー単位のポリシーは、個々のユーザー、グループ、および連絡先オブジェクトにのみ影響します。ユーザー単位のポリシーを展開するには、ポリシーを 1 つ以上のユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。詳細については、「[Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの割り当て](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)」を参照してください。

ユーザー単位のホスト ボイス メール ポリシーを操作する方法の詳細については、「Lync Server 管理シェル」のドキュメントに記載されている次のコマンドレットを参照してください。

  - [New-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [Get-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostedVoicemailPolicy)

## ユーザー単位のホスト ボイス メール ポリシーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  New-CsHostedVoicemailPolicy コマンドレットを実行して、ポリシーを作成します。たとえば、以下を実行します。
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    前の例では、ユーザー単位のスコープを使用してホスト ボイス メール ポリシーを作成し、次のパラメーターを設定しています。
    
      - **Identity** では、ポリシーの一意の識別子を指定します。これにはスコープも含まれます。 ユーザー単位のスコープを使用するポリシーの場合、このパラメーター値には単純な文字列 (ExRedmond など) を指定します。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Description** では、ポリシーに関する説明情報を指定します (オプション)。
    
      - **Organization** では、Lync Server 2013 ユーザーが所属する Exchange テナントのコンマ区切り一覧を指定します。各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。

## 関連項目

#### タスク

[Lync Server 2013 でのユーザー単位のホスト ボイス メール ポリシーの割り当て](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

