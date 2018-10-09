---
title: ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。 Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。 このコンテンツは、自分のメールボックス内の参加者の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: f9a18aaf556427ccc1fad2700b40f40ff057be6a
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450458"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>ビジネス会議のため、Skype に接続されている大容量のファイルを保持します。

Skype ビジネス会議、どの参加者を選択し、開いてできますし、ダウンロードのためにファイルを添付することができます。 Skype ビジネス会議のための添付ファイルはメールボックスを持つ証拠保全に、Office 365 リテンション ・ ポリシーが適用される、または Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている保留リストに配置されます。 任意の参加者のメールボックスに保持されます。&amp;コンプライアンス センターです。 このコンテンツは、自分のメールボックス内の参加者の**回復可能なアイテム**フォルダーに保存されます。
  
保留中のメールボックスに保持されるファイルはインデックスが、セキュリティ コンテンツの検索を実行している場合、したがって検索できる&amp;コンプライアンス センターの関係者のメールボックスを検索する場合。 ただし、30 MB より大きい添付ファイルは 2 つ以上のサイズの小さいファイルに分割するには、圧縮 (.zip) ファイルとして保存します。 これらの小さいファイルの*コンテンツ*は、検索用インデックス付けされていないと、コンテンツ検索では返されない可能性があります。 ただし、これらのファイル (ファイル名や作成者) などの*メタデータ*は、検索用インデックスが作成されて、コンテンツの検索で返される可能性があります。
  
> [!IMPORTANT]
> Skype からビジネス会議のための大規模なファイルを保持する機能、MaxReceiveSize と MaxSendSize の設定、Exchange Online のメールボックスに影響します。 MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と、35 MB です。 ただし、これらの既定の設定は、30 MB より大きいビジネス会議のため、Skype から任意のファイルを保持するには小さすぎます。 Exchange オンラインのメッセージの添付ファイルとその他のバイナリ データは Base64 エンコードを使用するためです。 メッセージをエンコードすると、そのサイズは約 33% 増加します。 したがって、Skype のビジネス ・ ミーティング用の大きなファイルを保存することを確認するには、お勧め MaxReceiveSize と MaxSendSize 39 MB (約 33%、30 MB サイズの上限値については、以前よりも大きい) には、両方の値を大きくことユーザーを保留リストに配置されます。 それ以外の場合、ビジネス会議のため、Skype に接続されているサイズの大きいファイルは保持されません可能性があります。 Exchange オンライン PowerShell で、**セット-メールボックス MaxReceiveSize**と**セットのメールボックスの MaxSendSize**コマンドを使用する方法の詳細については、[一連のメールボックス](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)を参照してください。
  
保留リストに記載されていないメールボックスは、会議データを保存を必要はありません。 などの 3 つの会議の参加者の 2 つのメールボックスが保持マークが付いている、会議データは、これら 2 つの参加者のメールボックスに保存されますが、3 つ目の参加者のメールボックスにメールボックスを持つではありませんを保持します。
  
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ブロック ポイント ツー ポイントのファイルの転送](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーを設定します](set-up-conferencing-policies-for-your-organization.md)
  
  
 