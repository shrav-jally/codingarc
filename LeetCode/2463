class Solution:
    def minimumTotalDistance(self, robot, factory):
        # Sort robots and factories by position
        robot.sort()
        factory.sort()

        # Flatten factory positions according to their capacities
        factory_positions = []
        for f in factory:
            for i in range(f[1]):
                factory_positions.append(f[0])

        # Recursively calculate minimum total distance
        return self._calculate_min_distance(0, 0, robot, factory_positions)

    def _calculate_min_distance(
        self, robot_idx, factory_idx, robot, factory_positions
    ):
        # All robots assigned
        if robot_idx == len(robot):
            return 0
        # No factories left to assign
        if factory_idx == len(factory_positions):
            return 1e12

        # Option 1: Assign current robot to current factory
        assign = abs(
            robot[robot_idx] - factory_positions[factory_idx]
        ) + self._calculate_min_distance(
            robot_idx + 1, factory_idx + 1, robot, factory_positions
        )

        # Option 2: Skip current factory for the current robot
        skip = self._calculate_min_distance(
            robot_idx, factory_idx + 1, robot, factory_positions
        )

        # Take the option with the minimum distance
        return min(assign, skip)
