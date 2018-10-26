---
title: 'Lync Server 2013: 公開プロバイダーに対するメディアの暗号化の構成'
TOCTitle: 公開プロバイダーに対するメディアの暗号化の構成
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48273230
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での公開プロバイダーに対するメディアの暗号化の構成

 

_**トピックの最終更新日:** 2014-12-12_

ライセンス要件およびプロビジョニング プロセスの実行方法の詳細については、「Microsoft Lync Server、Office Communications Server、および Live Communications Server のパブリック IM 接続のプロビジョニング ガイド」( <http://go.microsoft.com/fwlink/?linkid=155970>) を参照してください。

Windows Live Messenger との音声ビデオ (A/V) フェデレーションを実装する場合は、 Lync Server の暗号化レベルと EnablePublicCloudAccess ポリシーという 2 つのパラメーターを変更する必要があります。既定では、暗号化レベルは「必須」です。この設定を「サポート」に変更する必要があります。EnablePublicCloudAccess ポリシーが false に設定されている場合は、 **True** に変更する必要があります。この変更は、 Lync Server 管理シェルから実行できます。


> [!IMPORTANT]
> Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard Client Access License (CAL) を超えてユーザー/デバイス ライセンスを追加する必要はありません。翌年、Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。



## Windows Live のフェデレーションを構成する

1.  フロントエンド サーバーで Lync Server 管理シェルを起動します。そのためには、\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  コマンド プロンプトで、次の各コマンドを入力します。
    
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption

       &nbsp;
    
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    > [!NOTE]
    > Windows Live Messenger は、音声ビデオの暗号化をサポートしていないため、この手順は必ず実行する必要があります。このコマンドは、音声ビデオ データの暗号化を必須にするのではなく、グローバル ポリシーの暗号化設定を「サポート」に設定します。暗号化をサポートするクライアントは、この場合も Lync 2013 などの暗号化を使用します。

