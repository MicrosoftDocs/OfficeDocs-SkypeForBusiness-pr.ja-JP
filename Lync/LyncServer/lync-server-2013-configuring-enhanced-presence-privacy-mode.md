---
title: 拡張プレゼンス プライバシー モードの構成
TOCTitle: 拡張プレゼンス プライバシー モードの構成
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48274009
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 拡張プレゼンス プライバシー モードの構成

 

_**トピックの最終更新日:** 2016-12-08_

拡張プレゼンス プライバシー モードでは、ユーザーは Lync 2013 連絡先リストに掲載されている連絡先だけに自分のプレゼンス情報が表示されるように、プレゼンス情報を限定できます。このオプションは、**New-CsPrivacyConfiguration** および **Set-CsPrivacyConfiguration** コマンドレットの EnablePrivacyMode パラメーターで制御されます。EnablePrivacyMode が True に設定されている場合は、プレゼンス情報を連絡先に限定するオプションを Lync 2013 状態オプションで使用できるようになります。 EnablePrivacyMode が False に設定されている場合は、ユーザーがすべてのユーザーに対して自身のプレゼンス情報を常に表示できるようにするか、あるいは管理者がプライバシー モードに加える今後の変更に従うかのどちらかを選択できます。


> [!IMPORTANT]
> 以前のバージョン (Microsoft Office Communicator 2007 R2 または Microsoft Office Communicator 2007) では、Lync 2013 and Lync 2010 プライバシー設定は無効です。 Office Communicator の以前のバージョンによるサインインが可能である場合には、閲覧権限がないユーザーにも Lync 2013 ユーザーの状態、連絡先情報、またはピクチャが表示されます。 さらに、Lync 2013 ユーザーが以前のバージョンの Communicator であとからサインインすると、プライバシー設定はリセットされます。<BR>これらの理由から、移行シナリオでは、拡張プレゼンス プライバシー モードを有効にする前に、以下のことを実行してください。 
> <UL>
> <LI>
> <P>すべてのユーザーが Lync 2013 をインストールしたことを確認します。</P>
> <LI>
> <P>Communicator の以前のバージョンによるサインインを回避する、クライアント バージョンのポリシー ルールを定義します。</P></LI></UL>



## 拡張プレゼンス プライバシー モードを有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  次のコマンドを実行します。
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    このコマンドによって、組織で現在使用されているすべてのプライバシー構成設定のプライバシー モードが有効になります。

## 関連項目

#### その他のリソース

[Get-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set-CsPrivacyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPrivacyConfiguration)

