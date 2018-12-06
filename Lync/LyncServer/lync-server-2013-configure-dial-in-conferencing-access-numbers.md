---
title: 'Lync Server 2013: ダイヤルイン会議アクセス番号の構成'
TOCTitle: ダイヤルイン会議アクセス番号の構成
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48273725
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのダイヤルイン会議アクセス番号の構成

 

_**トピックの最終更新日:** 2011-07-17_

ダイヤルイン会議を展開するときには、ユーザーが公衆交換電話網 (PSTN) からダイヤルして電話会議のオーディオ部分に参加するための電話番号を設定する必要があります。 それらのダイヤルイン アクセス番号は、ミーティングの招待状と \[ダイヤルイン会議の設定\] Web ページに表示されます。

ダイヤルイン アクセス番号を作成する前に、まずダイヤルイン会議の域を計画し、その地域のダイヤル プランを構成する必要があります。地域の詳細については、「計画」のドキュメントの「[Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)」を参照してください。ダイヤルイン会議のダイヤル プランの構成に関する詳細については、「[Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)」を参照してください。

> [!NOTE]
> 新しいダイヤルイン アクセス番号は、そのアクセス番号の Active Directory ドメイン サービス (AD DS) レプリケーションが完了するまで使用できません。 レプリケーションが完了するまでに数時間かかることがあります。


> [!NOTE]
> ダイヤルイン アクセス番号を作成した後は、Active Directory の連絡先オブジェクトの表示名を変更し、ユーザーが正しいアクセス番号を識別しやすくすることができます。 表示名を変更するには、<strong>Set-CsDialInConferencingAccessNumber</strong> コマンドレットを使用します。 Active Directory のオブジェクトは手動で変更しないでください。 <strong>Set-CsDialInConferencingAccessNumber</strong> コマンドレットを使用したアクセス番号の変更の詳細については、Lync Server 管理シェルのドキュメントを参照してください。


## このセクション中

[Lync Server 2013 でのダイヤルイン会議アクセス番号の作成または変更](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

## 関連項目

#### 概念

[Lync Server 2013 でのダイヤルイン会議の要件](lync-server-2013-dial-in-conferencing-requirements.md)  

#### その他のリソース

[Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

