---
description: Trigger nodes start workflows based on events or when a condition is met.
contentType: howto
---

# Trigger nodes

Trigger nodes start your workflow.
They run on events or on specific conditions.
Every workflow needs at least one trigger node.

## Trigger types

* **Manual**:
  The [Manual Trigger](/integrations/builtin/core-nodes/n8n-nodes-base.manualworkflowtrigger.md) node runs only if you select **Execute workflow** or **Execute step** in n8n.
  Use this trigger to test your workflows,
  or for workflows that shouldn't run automatically.
  Every workflow can include only one Manual Trigger node.

* **Schedule**:
  The [Schedule Trigger](/integrations/builtin/core-nodes/n8n-nodes-base.scheduletrigger/index.md) node runs at specific times you define.

* **Events**:
  Most triggers run when they receive events from users or external services.

    * **User interactions**:
	  Triggers such as the [Chat Trigger](/integrations/builtin/core-nodes/n8n-nodes-langchain.chattrigger/index.md) or the [n8n Form Trigger](/integrations/builtin/core-nodes/n8n-nodes-base.formtrigger.md) nodes run when they receive user input.

	* **Webhook**:
	  The [Webhook node](/integrations/builtin/core-nodes/n8n-nodes-base.webhook/index.md) exposes a URL that you or other services can call to start the workflow.
	  Many app event triggers build on top of this node.

    * **App events**:
	  Triggers that listen for events from third-party services.
	  For example, the [Slack Trigger](/integrations/builtin/app-nodes/n8n-nodes-base.slack.md) is based on the Webhook node and expses app-specific events, for example, when a message is posted to a Slack channel.
      For a list of available triggers, browse the [Triggers library](/integrations/builtin/trigger-nodes/index.md).

## Identify trigger nodes

Trigger nodes look different from action nodes:

* Trigger nodes have a rounded left edge and no input.
* Trigger nodes have a bolt icon <span class="n8n-inline-image">![Trigger icon](/_images/common-icons/trigger.png){.off-glb}</span> on the left.

<figure markdown="span">
![Screenshot of the Schedule Trigger node](/_images/workflows/components/trigger-nodes/trigger-node.png)
<figcaption>Trigger nodes are rounded and have a bolt icon instead of input.</figcaption>
</figure>

## Add trigger nodes to your workflow

### Add a trigger to an empty workflow

1. Select **Add first step**.
   n8n opens the nodes panel,
   where you can search or browse [trigger nodes](/glossary.md#trigger-node-n8n).

2. Select the trigger you want to use.

    /// note | Choose the correct app event
	If you select **On app event**,
	n8n shows a list of supported services.
	Use this list to browse n8n's integrations and trigger a workflow when your chosen service emits an event.
	Not all integrations include triggers.
	To check, select the node.
	If triggers are available,
	you'll see them at the top of the available operations list.

	For example, this is the trigger for Asana:

	![Screenshot of the Asana node operations list, showing the Recommended section at the top of the list](/_images/workflows/components/nodes/recommended-trigger.png)
	///

### Add another trigger to an existing workflow

1. Select the **Add node** <span class="n8n-inline-image">![Add node icon](/_images/try-it-out/add-node-small.png){.off-glb}</span> connector.
   n8n opens the nodes panel.

1. Select **Add another trigger**, then choose the trigger you want to add.

## Executions

Most triggers have two main modes: manual and production.
Manual execution is useful for testing workflows.
Some triggers, such as the [Error Trigger](/integrations/builtin/core-nodes/n8n-nodes-base.errortrigger.md)
provide test data to the workflow if you trigger them manually.
To run triggers in production, you must make the workflow **Active**.
For more information, see [Manual, partial, and production executions](/workflows/executions/manual-partial-and-production-executions.md).

