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

