---
title: Lync Server 2013 でのグローバル ホスト ボイス メール ポリシーの変更
TOCTitle: Lync Server 2013 でのグローバル ホスト ボイス メール ポリシーの変更
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48273958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのグローバル ホスト ボイス メール ポリシーの変更

 

_**トピックの最終更新日:** 2012-09-24_

グローバルなホスト ボイス メール ポリシーは、Lync Server 2013 と一緒にインストールされます。グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。 グローバル ポリシーを変更するには、Set-CsHostedVoicemailPolicy コマンドレットを使用して、パラメーターを固有の展開に合わせた値に設定します。

[Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostedVoicemailPolicy) コマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。

## グローバル ホスト ボイス メール ポリシーを変更するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsHostedVoicemailPolicy コマンドレットを実行して、グローバル ポリシー パラメーターを環境に合わせた値に設定します。たとえば、以下を実行します。
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    このコマンドはポリシーの Identity パラメーターを指定しないため、Windows PowerShell コマンドライン インターフェイス がグローバルなホスト ボイス メール ポリシーに対して次の各値を設定します。
    
      - **Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。
    
      - **Organization** では、Lync Server ユーザーが所属する Exchange テナントのコンマ区切り一覧を指定します。各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。
    
    > [!NOTE]
    > 前のサンプル コマンドレットでは、値 &quot;corp1.litwareinc.com&quot; を Organization パラメーターに既に存在する可能性がある任意の値と入れ替えてあります。 たとえば、ポリシーが組織のコンマ区切りのリストを既に含んでいる場合は、リスト全体を入れ替えます。 リスト全体を入れ替えるのではなくリストに組織を追加する場合は、次のようなコマンドを実行します。</td>
    </tr>
    </tbody>
    </table>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

