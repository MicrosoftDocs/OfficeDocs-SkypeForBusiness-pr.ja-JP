---
title: クライアント コンピューターの個人連絡先ストアの構成
TOCTitle: クライアント コンピューターの個人連絡先ストアの構成
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49887201
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# クライアント コンピューターの個人連絡先ストアの構成

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する場合、Microsoft Lync 2010 を実行する任意のクライアント コンピューターに個人連絡先ストアを構成することをお勧めします。具体的には、Exchange を個人連絡先ストアとして使用するよう Lync を構成し、同時にユーザーがその決定を上書きできないようにする必要があります。そのためには、各クライアント コンピューターでレジストリ値を作成して構成します。

これは、Lync 2013 を実行しているコンピューターでは必要ありません。

ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。

1.  クライアント コンピューターで \[スタート\] ボタンをクリックし、\[ファイル名を指定して実行\] をクリックします。

2.  \[ファイル名を指定して実行\] ダイアログ ボックスで「regedit」と入力し、Enter キーを押します。

3.  レジストリ エディターで、 \[**HKEY\_LOCAL\_MACHINE**\]、\[**Software**\]、\[**Policies**\]、\[**Microsoft**\]、\[**Communicator**\] の順に展開します。

4.  \[**Communicator**\] を右クリックし、\[**新規**\] をポイントし、\[**DWORD (32 ビット) 値**\] をクリックします。

5.  新しい値を作成した後に「PersonalContactStoreOverride」と入力し、Enter キーを押して値の名前を変更します。

6.  PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディターを閉じます。

複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。詳細については、「グループ ポリシー」のドキュメント ([http://go.microsoft.com/fwlink/?linkid=268543\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268543%26clcid=0x411)) を参照してください。

