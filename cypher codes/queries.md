# Queries

    'artifacts': """
        MATCH (a:Artifact)
        RETURN
            a.id AS artifact_id,
            a.found AS artifact_found
    """,
    'releases': """
        MATCH (rel:Release)
        RETURN
            rel.id AS release_id,
            rel.version AS release_version,
            rel.timestamp AS release_timestamp
    """,
    'dependencies': """
        MATCH (rel:Release)-[d:dependency]->(depArtifact:Artifact)
        RETURN
            rel.id AS release_id,
            d.scope AS dependency_scope,
            d.targetVersion AS dependency_target_version,
            depArtifact.id AS dependency_artifact_id
    """,
    'added_values': """
        MATCH (rel:Release)-[:addedValues]->(av:AddedValue)
        RETURN
            rel.id AS release_id,
            av.id AS added_value_id,
            av.type AS added_value_type,
            av.value AS added_value
    """,
    'artifact_release': """
        MATCH (a:Artifact)-[:relationship_AR]->(rel:Release)
        RETURN
            a.id AS artifact_id,
            rel.id AS release_id
    """



## 

    'added_values': """
        MATCH (rel:Release)-[:addedValues]->(av:AddedValue)
        RETURN
            rel.id AS release_id,
            av.id AS added_value_id,
            av.type AS added_value_type,
            av.value AS added_value

This code returns 43377417 values. But in the main msr website, the added value mentioned is 44,035,495

Upon furher investigation, we found that there are 658,078 AddedValue nodes that are not connected to any Release node via the addedValues relationship.  The discrepancy arises because  original query only retrieves AddedValue nodes that are connected to Release nodes via the addedValues relationship.

Total AddedValue Nodes: 44,035,495
AddedValue Nodes Connected to Release: 43,377,417
Unconnected AddedValue Nodes: 44,035,495 - 43,377,417 = 658,078