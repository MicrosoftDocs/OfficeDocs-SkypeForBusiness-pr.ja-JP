---
title: 割り当てられていない電話番号の構成
TOCTitle: 割り当てられていない電話番号の構成
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48273016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 割り当てられていない電話番号の構成

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server では、組織で有効であるがユーザーや電話に割り当てられていない電話番号に通話の着信があったときの動作を構成できます。そのような通話の処理を構成するには、割り当てられていない番号の表を設定します。その表を使用して、それらの通話をアナウンス アプリケーションまたは Exchange UM サーバーにルーティングできます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。 組織の有効な内線番号すべて、割り当てられていない内線番号のみ、または両方の種類の番号の組み合わせで、この表を構成できます。 割り当てられていない番号の表には、割り当てられている番号と割り当てられていない番号を両方入れることができますが、現在割り当てられていない番号を発信者がダイヤルしたときのみ呼び出されます。 有効な内線番号すべてを割り当てられていない番号の表に入れる場合、テーブルを再構成しなくても、ユーザーが組織を離れたとき必ず行う処理を指定できます。 割り当てられていない内線番号を表に入れる場合、特定の番号について行う処理を調整できます。 たとえば、顧客サービス デスクの内線番号を変更する場合、古い顧客サービス番号を表に入れ、新しい番号を知らせるアナウンスをそれに割り当てることができます。


> [!IMPORTANT]
> 割り当てられていない番号の表を構成する前に、アナウンスを 1 つ以上既に定義しているか、Exchange UM の自動応答を設定する必要があります。アナウンスの作成の詳細については、「<A href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でのアナウンスの作成</A>」を参照してください。Exchange UM 設定が構成されているかどうかを確認するには、<STRONG>Get-CsExUmContact</STRONG> コマンドレットを実行します。詳細については、「<A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>」を参照してください。



## このセクション中

  - [Lync Server 2013 での割り当てられていない番号範囲の作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [割り当てられていない番号の範囲の削除](lync-server-2013-delete-an-unassigned-number-range.md)

