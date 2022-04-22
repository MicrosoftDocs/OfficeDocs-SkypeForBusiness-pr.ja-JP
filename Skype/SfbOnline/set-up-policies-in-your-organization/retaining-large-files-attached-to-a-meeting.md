---
title: Skype for Business会議に添付された大きなファイルを保持する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype for Business会議にファイルを添付すると、参加者は開いてダウンロードできます。 Skype for Business会議に添付されたファイルは、メールボックスが訴訟ホールドに配置されているか、Microsoft 365またはOffice 365アイテム保持ポリシーが適用されているか、Microsoft Purview コンプライアンス ポータルの電子情報開示ケースに関連付けられたホールドに配置されている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス内の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031872"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Skype for Business会議に添付された大きなファイルを保持する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype for Business会議にファイルを添付すると、参加者は開いてダウンロードできます。 Skype for Business会議に添付されたファイルは、メールボックスが訴訟ホールドに配置されているか、Microsoft 365またはOffice 365アイテム保持ポリシーが適用されているか、Microsoft Purview コンプライアンス ポータルの電子情報開示ケースに関連付けられたホールドに配置されている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス内の **回復可能なアイテム** フォルダーに保存されます。
  
保留中のメールボックスに保持されているファイルはインデックスが作成されるため、参加者のメールボックスを検索するときにセキュリティ &amp; コンプライアンス センターでコンテンツ検索を実行するときに検索できます。 ただし、30 MB を超える添付ファイルは、2 つ以上の小さいファイルに分割され、圧縮 (.zip) ファイルとして保存されます。 これらの小さいファイルの  *コンテンツ*  は、検索用にインデックスが作成されず、コンテンツ検索では返されない可能性があります。 ただし、これらのファイルの *メタデータ*  (ファイル名や作成者など) は、検索用にインデックスが作成され、コンテンツ検索で返される場合があります。
  
> [!IMPORTANT]
> Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、Skype for Business会議から大きなファイルを保持する機能に影響を与える可能性があります。 MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と 35 MB です。 ただし、これらの既定の設定は小さすぎて、30 MB を超えるSkype for Business会議のファイルを保持するには小さすぎます。 これは、Exchange Onlineがメッセージ添付ファイルとその他のバイナリ データの Base64 エンコードを使用するためです。 メッセージがエンコードされると、そのサイズは約 33% 増加します。 そのため、Skype for Business会議の大きなファイルを確実に保持するには、保留になっているユーザーに対して、MaxReceiveSize と MaxSendSize の両方の値を 39 MB (前述の 30 MB サイズ制限より約 33% 大きい) に増やすことをお勧めします。 それ以外の場合、Skype for Business会議に添付された大きなファイルは保持されない可能性があります。 PowerShell **で Set-Mailbox -MaxReceiveSize** コマンドと **Set-Mailbox -MaxSendSize** コマンドを使用する方法の詳細については、「Exchange Online [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)」を参照してください。
  
保留になっていないメールボックスには、会議データは保存されません。 たとえば、2 人の参加者のメールボックスが保持対象としてマークされている 3 人の会議では、会議データは 2 人の参加者のメールボックスに保存されますが、メールボックスが保留になっていない 3 番目の参加者のメールボックスには保存されません。
  
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイントからポイントへのファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)
  
  
