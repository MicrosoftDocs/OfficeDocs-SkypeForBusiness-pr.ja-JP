---
title: Lync Server 2013 でのボイス メール エスケープの構成
TOCTitle: Lync Server 2013 でのボイス メール エスケープの構成
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49887079
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのボイス メール エスケープの構成

 

_**トピックの最終更新日:** 2013-02-22_

ユーザーが携帯電話への同時着信を構成している場合、携帯電話がオフになっている、バッテリが切れている、または圏外になっているときは、通常、発信者はユーザーの個人ボイス メールにルーティングされます。Microsoft Lync Server 2013 では、ユーザーは仕事関係の呼び出しが会社のボイス メール システムにルーティングされるように選択できます。具体的には、タイマーを構成でき、定義されている時間の範囲内で通信会社のボイス メールが通話に応答した場合、Lync Server 2013 は通信会社のボイス メール システム (およびユーザーの個人ボイス メール) からは切断しますが、ユーザーの会社システム内の残りのエンドポイントは呼び出しを続けます。これにより、発信者は自動的にユーザーの会社のボイス メールにルーティングされます。

この構成を行うには、Lync Server 管理シェルのコマンドレット Set-CsVoicePolicy を音声ポリシー レベルで使用します。パラメーターは次のとおりです。

## ボイス メール エスケープの構成

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **Set-CsVoicePolicy** に対して次のパラメーターを指定します。
    
      - **EnableVoicemailEscapeTimer** - エスケープ タイマーを有効または無効にします。
    
      - **PSTNVoicemailEscapeTimer** - タイムアウト値をミリ秒単位で指定します。既定値は 1500 ミリ秒で、指定できる値の範囲は 0 ～ 8000 ミリ秒です。

## 例

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

## 関連項目

#### その他のリソース

[Lync Server 2013 での通話機能と特権の承認のための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

